## Purpose
This is a web service skeleton app.

## Project structure
```
WebService/
│
├── app/
│   ├── __init__.py
│   ├── main.py         # Main web service file
│   └── models.py       # Database models for messages and conversation (optional, for the future)
│
├── .gitignore          # Add filenames you do not want to be added to your repository here
├── requirements.txt    # Dependencies
└── README.md           # The file you are reading right now :)
```

## Project setup

### Install Python
[https://www.python.org/downloads/](https://www.python.org/downloads/])

### Check Python version, it should be 3.1x
`python3 --version`

### Get the code from the GitHub repository

Create a github repository, for example:  
github.com/username/my-web-service-client  
  
Create a local folder for keeping your project:
```
mkdir my-web-service-client
cd my-web-service-client
```

Run this command in Terminal (inside the same folder):
```
git clone https://github.com/ingus-t/rtu-web-service
```

After cloning, you need to add your repository as the remote origin. Run the following command, replacing [your_username] and [your_repository_name] with your actual GitHub username and repository name:
```
git remote add origin git@github.com:[your_username]/[your_repository_name].git
```

To ensure the remote was added correctly, run:
```git remote -v```

Push the code to your repository:
```git push -u origin master```

### Create environment
If you use an environment, all dependencies you install will be added to this environment and not be installed globally.
Alternatives for environment management are Poetry, vu, and other tools.
```python3 -m venv [environment_name]```

### Activate environment
Linux:  
```
source [environment_name]/bin/activate
```

Windows:  
```
[environment_name]\Scripts\activate
```

### Install dependencies
```
pip install -r requirements.txt
```  
or  
```
python -m pip install -r requirements.txt
```

### Start the app
```
uvicorn app.main:app --reload
```

### Access the documentation of your web service
Visit [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs) in your browser to see the automatically generated API documentation from FastAPI. You will be able to test the two endpoints (/send_message/ and /conversation_history/) directly from the browser.

## (Optional) make the web service available on the internet
A locally hosted client will easily be able to use a locally hosted web service, but a mobile app will not be able to (localhost is not available on your phone!).
This step is important for those who will use Expo to build their mobile app.

### Install ngrok
[https://ngrok.com/](https://ngrok.com/)

### Use ngrok
This command will create a tunnel from your locally hosted web service (and the specific port!), and make it available online via a temporary URL (for example, https://ab12-a1-ab1-ab1-a1.ngrok-free.app ).
```
ngrok http http://localhost:8000
```
This is useful for development/testing on a small team.