#Lab: Google Cloud Fundamentals: Getting Started with App Engine

##Objectives:

In this lab, you learn how to perform the following tasks:

- Initialize App Engine.
- Preview an App Engine application running locally in Cloud Shell.
- Deploy an App Engine application, so that others can reach it.
- Disable an App Engine application, when you no longer want it to be visible.

Step 1:

Activate Google Cloud Shell.

To list the active account name use:

> gcloud auth list

This way we can find out on which project ID we are working on.

Step 2:

Initialize your App Engine app

> gcloud app create --project=$DEVSHELL_PROJECT_ID

Clone the source code repository 

> git clone https://github.com/GoogleCloudPlatform/python-docs-samples

Navigate to the source directory:

> cd python-docs-samples/appengine/standard_python3/hello_world

Step 3:

Run Hello World application locally - 

Execute the following command to download and update packages list.

> sudo apt-get update

Set up a virtual environment in which you will run your application. 

> sudo apt-get install virtualenv

Followed by

> virtualenv -p python3 venv

Activate the virtual environment.

> source venv/bin/activate

Navigate to your project directory and install dependencies:

> pip install  -r requirements.txt

Run the app

> python main.py

Step 4:

Deploy and run Hello World App Engine

Navigate to the source directory:

> cd ~/python-docs-samples/appengine/standard_python3/hello_world

Deploy app.

> gcloud app deploy

To view your app execute the following command: 

> gcloud app browse



Step 5:

Disable application:

> gcloud projects stop -q