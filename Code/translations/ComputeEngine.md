# LAB: Google Cloud Fundamentals: Getting Started with Compute Engine
---
## Objectives:
---


*In this lab, you learn how to perform the following tasks:*

- Create a Compute Engine virtual machine using the Google Cloud Platform (GCP) Console.

- Create a Compute Engine virtual machine using the gcloud command-line interface.

- Connect between the two instances

---
## STEPS TO CREATE A VIRTUAL MACHINE USING THE GCP CONSOLE
---


1. In the Navigation menu, click **Compute Engine > VM instances**.


2. Click **Create**


3. On the **Create an Instance** page, for **Name**, type _my-vm-1_

---
## STEPS FOR PREVIEWING AN APP ENGINE APPLICATION RUNNING LOCALLY IN CLOUD SHELL
---

1. Run Hello World application locally

	    sudo apt-get update


2. Set up a virtual environment in which you will run your application. Python virtual environments are used to isolate package installations from the system

	      sudo apt-get install virtualenv


* If prompted [Y/n], press Y and then Enter.

	   virtualenv -p python3 venv


3. Activate the virtual environment.

	    source venv/bin/activate


4. Navigate to your project directory and install dependencies.

	     pip install  -r requirements.txt


5. Run the application:

	    python main.py
6. In Cloud Shell, click Web preview (Web Preview) > Preview on port 8080 to preview the application


7. To end the test, return to Cloud Shell and press Ctrl+C to abort the deployed service.


8. Using the Cloud Console, verify that the app is not deployed. In the Cloud Console, on the Navigation menu (Navigation menu), click App Engine > Dashboard.

---
## STEPS FOR DEPLOYING AND RUNNING HELLO WORLD ON APP ENGINE 
---
* To deploy your application to the App Engine Standard environment:

1. Navigate to the source directory:
	
	    cd ~/python-docs-samples/appengine/standard_python3/hello_world

2. Deploy your Hello World application.

	   gcloud app deploy

* If prompted "Do you want to continue (Y/n)?", press Y and then Enter.(This app deploy command uses the app.yaml file to identify project configuration)

3. Launch your browser to view the app at http://YOUR_PROJECT_ID.appspot.com

	   gcloud app browse
* Congratulations! You created your first application using App Engine.

#  Click Check my progress to verify the objective.

---
## STEPS FOR DISABLING THE APPLICATION
---
*  App Engine offers no option to Undeploy an application. After an application is deployed, it remains deployed

* However, you can disable the application, which causes it to no longer be accessible to users.

1. In the Cloud Console, on the Navigation menu (Navigation menu), click App Engine > Settings.


2. Click Disable application.


3. Read the dialog message. Enter the App ID and click DISABLE.


* If you refresh the browser window you used to view to the application site, you'll get a 404 error.

##  Congratulations!
*  You created your first application using App Engine!