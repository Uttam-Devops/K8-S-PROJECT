Flask Application with PostgreSQL Database
This is a simple Flask application that connects to a PostgreSQL database and allows inserting and retrieving users through API endpoints.

Requirements
Python 3.x
PostgreSQL database
Flask
Flask-SQLAlchemy
Prerequisites
Before running the app, ensure you have:

A PostgreSQL instance running and accessible.
Created a database named mono2micro (or modify the database name as per your requirements).
Setup Instructions
Step 1: Clone or Download the Repository
If you haven't done so already, download or clone this repository to your local machine.

bash
Copy
Edit
git clone <repository_url>
cd <repository_directory>
Step 2: Install Dependencies
Use pip to install the required dependencies.

bash
Copy
Edit
pip install -r requirements.txt
You can create a requirements.txt file with the following content:

makefile
Copy
Edit
Flask==2.2.3
Flask-SQLAlchemy==3.0.2
psycopg2-binary==2.9.3
Step 3: Configure PostgreSQL Database Connection
Update the SQLALCHEMY_DATABASE_URI configuration in the app.py file with your PostgreSQL connection string.

python
Copy
Edit
app.config['SQLALCHEMY_DATABASE_URI'] = 'postgresql://user1:Localhost_1234567@34.27.54.14:5432/mono2micro'
Make sure to replace:

user1: Your PostgreSQL username.
Localhost_1234567: Your PostgreSQL password.
34.27.54.14: Your PostgreSQL host.
5432: The port where PostgreSQL is running (default is 5432).
mono2micro: The name of the database.
Step 4: Run the Application
To run the Flask application, execute the following command:

bash
Copy
Edit
python app.py
By default, the application will start on http://localhost:5000.

Step 5: API Endpoints
Add a new user (POST request to /add_user):

Request body (JSON):
json
Copy
Edit
{
    "username": "new_user",
    "email": "new_user@example.com"
}
Response:
json
Copy
Edit
{
    "message": "User added successfully!"
}
Get all users (GET request to /get_users):

Response:
json
Copy
Edit
[
    {
        "id": 1,
        "username": "new_user",
        "email": "new_user@example.com"
    }
]
Step 6: Database Table Creation
On each request, the application ensures the users table is created in the database. The table has the following columns:

id: Integer, primary key.
username: String, unique and not nullable.
email: String, unique and not nullable.
The add_user route inserts new users into this table, and the get_users route fetches all existing users.

Step 7: Stop the Application
To stop the Flask application, press Ctrl+C in your terminal.

