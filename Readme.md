# Flask Application with PostgreSQL Database

This is a simple Flask application that connects to a PostgreSQL database and exposes API endpoints for adding and retrieving users.

## Prerequisites

Before you begin, ensure you have the following:

- Python 3.x installed on your machine
- PostgreSQL installed and running
- Basic knowledge of Flask and PostgreSQL

## Setup Instructions

### Step 1: Clone or Download the Repository

Clone or download the project to your local machine.

```bash
git clone <repository_url>
cd <repository_directory>
Step 2: Create a Virtual Environment (Optional but Recommended)
It's a good practice to use a virtual environment to manage project dependencies. To create a virtual environment, run:

bash
Copy
Edit
python3 -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
Step 3: Install Dependencies
Use pip to install the required dependencies.

bash
Copy
Edit
pip install -r requirements.txt
If you don't have a requirements.txt file, create one with the following content:

makefile
Copy
Edit
Flask==2.2.3
Flask-SQLAlchemy==3.0.2
psycopg2-binary==2.9.3
Install dependencies using:

bash
Copy
Edit
pip install flask flask-sqlalchemy psycopg2-binary
Step 4: Configure the Database Connection
Open the app.py file and update the SQLALCHEMY_DATABASE_URI with your PostgreSQL credentials.

python
Copy
Edit
app.config['SQLALCHEMY_DATABASE_URI'] = 'postgresql://user1:Localhost_1234567@34.27.54.14:5432/mono2micro'
Replace the following:

user1: Your PostgreSQL username.
Localhost_1234567: Your PostgreSQL password.
34.27.54.14: PostgreSQL host address.
5432: PostgreSQL port (default is 5432).
mono2micro: Database name.
Step 5: Run the Application
To run the Flask application, use the following command:

bash
Copy
Edit
python app.py
The application will start on http://localhost:5000.

Step 6: API Endpoints
The application exposes the following endpoints:

1. Add a new user (POST request to /add_user)
To add a new user, send a POST request with JSON data containing username and email:

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
2. Get all users (GET request to /get_users)
This endpoint returns a list of all users in the users table.

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
Step 7: Database Table
The users table is automatically created before every request. It includes the following fields:

id: Integer, primary key.
username: String, unique and not nullable.
email: String, unique and not nullable.
Step 8: Stopping the Application
To stop the application, press Ctrl+C in your terminal.

Troubleshooting
If you encounter any issues:

Make sure your PostgreSQL server is running.
Ensure your database credentials are correct.
Check if the necessary packages are installed.
License
This project is licensed under the MIT License - see the LICENSE file for details.

markdown
Copy
Edit

### Usage:

1. Save this as `README.md` in your project folder.
2. Ensure that `requirements.txt` contains the necessary dependencies.
3. Provide your PostgreSQL credentials in the `app.py` file.

Let me know if you need anything else!
