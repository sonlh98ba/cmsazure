# Article CMS (FlaskWebProject)

## Application URL

[Application Click here](https://cmswebappfsoft.azurewebsites.net/)

This project is a Python web application built using Flask. The user can log in and out and create/edit articles. An article consists of a title, author, and body of text stored in an Azure SQL Server along with an image that is stored in Azure Blob Storage. You will also implement OAuth2 with Sign in with Microsoft using the `msal` library, along with app logging.

## Log In Credentials for FlaskWebProject

- Username: admin
- Password: pass

Or, once the MS Login button is implemented, it will automatically log into the `admin` account.

![login with pass](example_images/login_with_pass.png)
![login with ad](example_images/login_with_ad.png)

After your login successful, you get to the home page
![home page](example_images/homepage.png)

## Project Instructions (For Student)

You are expected to do the following to complete this project:

1. Create a Resource Group in Azure.

  + Resource Group Name: Project_CMS
  + Location: Australia East


2. Create an SQL Database in Azure that contains a user table, an article table, and data in each table (populated with the scripts provided in the SQL Scripts folder).
  - Provide a screenshot of the populated tables as detailed further below.

- Article table

![article table](/example_images/articles_table.png)

- User Table

![article table](/example_images/users_table.png)

3. Create a Storage Container in Azure for `images` to be stored in a container.
  - Provide a screenshot of the storage endpoint URL as detailed further

- Screenshot

![screenshot ](/example_images/storage_ep.png)

4. Add functionality to the Sign In With Microsoft button.
  - This will require completing TODOs in `views.py` with the `msal` library, along with appropriate registration in Azure Active Directory.
 
- Updated view.py and config.py and tested the application locally with Azure active directory and database. Please refer [view.py](FlaskWebProject/views.py) 
 
5. Choose to use either a VM or App Service to deploy the FlaskWebProject to Azure. Complete the analysis template in `WRITEUP.md` (or include in the README) to compare the two options, as well as detail your reasoning behind choosing one or the other. Once you have made your choice, go through with deployment.

- The document is [here](WRITEUP.md)

6. Add logging for whether users successfully or unsuccessfully logged in.
  - This will require completing TODOs in `__init__.py`, as well as adding logging where desired in `views.py`.

Please refer code here [`__init__.py`](FlaskWebProject/__init__.py) and [`views.py`](FlaskWebProject/views.py)

7. To prove that the application in on Azure and working, go to the URL of your deployed app, log in using the credentials in this README, click the Create button, and create an article with the following data:

- Title: "Hello World!"
- Author: "Jane Doe"
- Body: "My name is Jane Doe and this is my first article!"
- Upload an image of your choice. Must be either a .png or .jpg.
  After saving, click back on the article you created and provide a screenshot proving that it was created successfully. Please also make sure the URL is present in the screenshot.

The List of the blogs below

8. Log into the Azure Portal, go to your Resource Group, and provide a screenshot including all of the resources that were created to complete this project. (see sample screenshot in "example_images" folder)

- See section below under screenshot

9. Take a screenshot of the Redirect URIs entered for your registered app, related to the MS Login button.

- See section below under screenshot
 
10. Take a screenshot of your logs (can be from the Log stream in Azure) showing logging from an attempt to sign in with an invalid login, as well as a valid login.

- See section below under screenshot

## example_images Folder

This folder contains sample screenshots that students are required to submit in order to prove they completed various tasks throughout the project.

1. article-cms-solution.png is a screenshot from running the FlaskWebProject on Azure and prove that the student was able to create a new entry. The Title, Author, and Body fields must be populated to prove that the data is being retrieved from the Azure SQL Database while the image on the right proves that an image was uploaded and pulled from Azure Blob Storage.

![Article CMS Solution](example_images/blog.png)

![ My blog](example_images/my_blog.png)

![blog list](example_images/blog_list.png)

2. azure-portal-resource-group.png is a screenshot from the Azure Portal showing all of the contents of the Resource Group the student needs to create. The resource group must (at least) contain the following:

- Storage Account
 - SQL Server
 - SQL Database
 - Resources related to deploying the app
![azure portal resource group](example_images/rg_details.png)

3. sql-storage-solution.png is a screenshot showing the created tables and one query of data from the initial scripts.
![tables and queries](example_images/sql-storage-solution.png)

  
4. blob-solution.png is a screenshot showing an example of blob endpoints for where images are sent for storage.

![blob solution](example_images/storage_acc_1.png)
![blob solution](example_images/storage_acc_2.png)
![ Storage Image](example_images/storage_ep_images.png)

5. uri-redirects-solution.png is a screenshot of the redirect URIs related to Microsoft authentication.

![uri redirect](example_images/uri-redirects-solution.png)

![ app registration](example_images/app_registraion_1.png)

6. log-solution.png is a screenshot showing one potential form of logging with an "Invalid login attempt" and "admin logged in successfully", taken from the app's Log stream. You can customize your log messages as you see fit for these situations.

![login](example_images/login_out.png)

![Invalid login](example_images/Invalid_login.png)

## Dependencies

1. A free Azure account
2. A GitHub account
3. Python 3.7 or later
4. Visual Studio 2019 Community Edition (Free)
5. The latest Azure CLI (helpful; not required - all actions can be done in the portal)

All Python dependencies are stored in the requirements.txt file. To install them, using Visual Studio 2019 Community Edition:

1. In the Solution Explorer, expand "Python Environments"
2. Right click on "Python 3.7 (64-bit) (global default)" and select "Install from requirements.txt"

## Troubleshooting

- Mac users may need to install `unixodbc` as well as related drivers as shown below:
 
  ```bash
  brew install unixodbc
  ```

- Check [here](https://docs.microsoft.com/en-us/sql/connect/odbc/linux-mac/install-microsoft-odbc-driver-sql-server-macos?view=sql-server-ver15) to add SQL Server drivers for Mac.
