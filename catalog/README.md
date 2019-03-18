# Item Catalog Web App
By Nallapati Aishwarya
This web app is a project for the Udacity [FSND Course](https://www.udacity.com/course/full-stack-web-developer-nanodegree--nd004).

## About
This project is a RESTful web application utilizing the Flask framework which accesses a SQL database that populates book categories and their editions. OAuth2 provides authentication for further CRUD functionality on the application. Currently OAuth2 is implemented for Google Accounts.
CRUD operations:
CRUD operations are nothing but creating ,reading ,updating and deleting the items


## In This Project
This project has one main Python module `main.py` which runs the Flask application. A SQL database is created using the `Data_Setup.py` module and you can populate the database with test data using `database_init.py`.
The Flask application uses stored HTML templates in the tempaltes folder to build the front-end of the application.

## Skills Required
1. Python
2. HTML
3. CSS
4. OAuth
5. Flask Framework
6.DataBaseModels
## Installation
There are some dependancies and a few instructions on how to run the application.
Seperate instructions are provided to get GConnect working also.

## Dependencies
- [Vagrant](https://www.vagrantup.com/)
- [Udacity Vagrantfile](https://github.com/udacity/fullstack-nanodegree-vm)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)



## How to Install
1. Install Vagrant & VirtualBox.
2. Clone the Udacity Vagrantfile.
3. Go to Vagrant directory and either clone this repo or download and place zip here.
3. Launch the Vagrant VM (`vagrant up`).
4. Log into Vagrant VM (`vagrant ssh`).
5. Navigate to `cd /vagrant` as instructed in terminal.
6. The app imports requests which is not on this vm. Run pip install requests.

Or you can simply Install the dependency libraries (Flask, sqlalchemy, requests,psycopg2 and oauth2client) by running .
`pip install -r requirements.txt`

7. Setup application database `python /item_catalogue/Data_Setup.py`.
here database is created.
8. *Insert sample data `python /item_catalogue/database_init.py`.
here data is inserted into database.
9. Run application using `python /item_catalogue/main.py`.
here server is activated by running main file.
10. Access the application locally using http://localhost:9999 in browser.

*Optional step(s)

## Using Google Login
To get the Google login working there are a few additional steps:

1. Go to [Google API Console](https://console.developers.google.com)
2. Sign up or Login if prompted.
3. Go to Credentials.
4. Select Create Crendentials > OAuth Client ID
5. Select Web application.
6. Enter name 'Universities'
7. Authorized JavaScript origins = 'http://localhost:9999'
8. Authorized redirect URIs = 'http://localhost:9999/login' && 'http://localhost:9999/gconnect'
9. Select Create
10. Copy the Client ID and paste it into the `data-clientid` in login.html
11. On the Dev Console Select Download JSON.
12. Rename JSON file to client_secrets.json
13. Place JSON file in item_catalogue directory that you cloned from here
14. Run application using `python /item_catalogue/main.py`

## JSON Endpoints
The following are open to the public:

allUniversitiesJSON: `/University/JSON`
    - Displays the whole Universities with college affiliated to that university.

Categories JSON: `/University/UniversityName/JSON`
    - Displays all Universities.
itemsJSON: `/University/universities/JSON`
	- Displays all Colleges.

categoryItemsJSON: `/University/<path:college_name>/universities/JSON`
    - Displays Colleges affiliated to given University.

ItemJSON: `/University/<path:university_name>/<path:universitycollege_name>/JSON`
    - Displays a specific given college of given University.

