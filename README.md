# NutriSmart
**Smart Nutrition Control** — An application for personal nutrition tracking, BMI monitoring, and AI-assisted diet planning, built with Python and Tkinter.

## Features
- **User Authentication** — Register and log in securely; supports both regular users and admin accounts.
- **Health Profile & BMI Calculator** — Enter personal details (age, weight, height, gender, activity level, health goal, and health conditions) and instantly calculate your BMI with a color-coded category rating.
- **Food Log** — Search from a built-in food database and log meals by type (breakfast, lunch, dinner, snack) with quantity tracking.
- **Diet Plan Generator** — Calculates your daily calorie target using the Harris-Benedict equation and generates a personalized meal plan from the food database.
- **Nutritional Analysis** — Visualizes your eating habits with embedded Matplotlib charts:
  - Weekly calorie bar chart
  - Macronutrient pie chart (protein, carbs, fat)
  - Today's nutrition summary
- **Admin Panel** — Manage registered users and the food database (add, edit, and delete food items).

## Tech Stack
 Language:   Python 3
 GUI     :  Tkinter / ttk 
 Database:   MySQL 
 Charts  :  Matplotlib 
 DB Driver:  mysql-connector-python 

## Project Structure
Nutri_Smart/
├── main.py         
├── config.py     
├── database.py 
├── database.sql   
├── test_db.py     
└── modules/
    ├── auth.py    
    ├── profile.py  
    ├── food_log.py 
    ├── diet_plan.py  
    ├── analysis.py  
    ├── food_db.py  
    └── admin.py   

## Prerequisites
- Python 3.8+
- MySQL Server (running locally)
- The following Python packages:
    mysql-connector-python
    matplotlib
-Install them with:
pip install mysql-connector-python matplotlib

## Setup
**1. Extract the project**
unzip Nutri_Smart.zip
cd Nutri_Smart

**2. Set up the database**
Open your MySQL client and run the provided SQL file:
mysql -u root -p < database.sql

This creates the `nutrismart` database, all required tables, and inputs the food database with sample items. It also creates a default admin account.

**3. Configure the database connection**
Open `config.py` and update the credentials to match your local MySQL setup:
python
DB_CONFIG = {
    "host": "localhost",
    "user": "root",
    "password": "your_password_here",
    "database": "nutrismart"
}

**4. Run the application**
python main.py

## Default Admin Account
 Username  Password 
 admin     admin123

## Database Schema
Table      Description 
users      Login credentials and roles (user / admin) 
profiles   Health data per user (age, weight, height, goals, conditions) 
foods      Food items with calorie and macronutrient data
food_logs  Daily meal entries linking users to food items
diet_plans Generated meal plan recommendations per user

## Supported Health Conditions
The profile module accommodates the following conditions, which influence diet plan recommendations:
- None
- Diabetes
- Hypertension
- Obesity
- Heart Disease
