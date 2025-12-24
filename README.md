Virtual Doctor Application
A Python-based Virtual Doctor application that uses decorators as the core implementation technique for menu handling and service registration.

🚀 Overview
This project demonstrates advanced Python decorator patterns by implementing a Virtual Doctor assistant with a clean web interface. The application uses decorators to dynamically register services, manage menus, and handle user routing without traditional if-else or switch statements.

✨ Features
Backend (Python)
Decorator-based architecture: All menu handling and service registration through decorators

Virtual Doctor services:

Symptom checking with general guidance

Basic health and wellness tips

Exercise and fitness recommendations

Common medicine information (non-diagnostic)

First aid guidance and emergency contacts

Dynamic menu system: Menus generated automatically from decorator-registered functions

Clean separation of concerns: Each service is a separate function wrapped by decorators

Frontend (HTML/CSS)
Responsive design: Works on desktop and mobile devices

Service cards: Visually appealing service selection

Interactive interface: Real-time input and results display

Minimal JavaScript: Primarily CSS and HTML with basic interactivity

🛠️ Technology Stack
Python 3.8+: Core application logic

HTML5 & CSS3: Frontend interface

No external dependencies: Pure Python and vanilla web technologies

Decorator Pattern: Core architectural pattern

📂 Project Structure
text
virtual-doctor-app/
├── virtual_doctor.py          # Main Python application
├── virtual_doctor.html        # Web interface
├── README.md                  # This file
└── requirements.txt           # Python requirements (none required)
🏃‍♂️ Quick Start
Option 1: Console Application
bash
# Run the Python console application
python virtual_doctor.py
Option 2: Web Interface
bash
# Open the HTML file in any web browser
# Double-click virtual_doctor.html or open with:
python -m webbrowser virtual_doctor.html
🎯 Core Decorator Implementation
The application's heart is the @virtual_doctor_service decorator:

python
def virtual_doctor_service(description, menu="main", requires_input=False):
    def decorator(func):
        # Register function in menu system
        if menu not in menu_options:
            menu_options[menu] = {}
        menu_options[menu][func.__name__] = {
            'function': func,
            'description': description,
            'requires_input': requires_input
        }
        
        def wrapper(*args, **kwargs):
            # Handle user input and execute service
            if requires_input:
                user_input = input("Please describe your concern: ")
                return func(user_input)
            return func()
        
        return wrapper
    return decorator
How Decorators Work in This Project:
Automatic Registration: Functions decorated with @virtual_doctor_service are automatically added to the menu system

Dynamic Menu Generation: The decorator stores service metadata used to build menus at runtime

Input Handling: Decorator can optionally collect user input before service execution

Service Isolation: Each service function remains independent and testable

📝 Example Service Definition
python
@virtual_doctor_service("Symptom Checker", requires_input=True)
def symptom_checker(user_input):
    """Analyze symptoms and provide general guidance"""
    # Service logic here
    return "Guidance based on: " + user_input
🎨 Frontend Features
Clean, Professional Design: Medical-themed color scheme

Responsive Layout: Adapts to different screen sizes

Interactive Cards: Clickable service cards with hover effects

Real-time Results: Dynamic display of virtual doctor responses

Emergency Information: Prominent display of emergency contacts

📋 Menu System
The application features a hierarchical menu system:

text
MAIN MENU
├── 1. Symptom Checker
├── 2. Health Guidance Menu
│   ├── Basic Health Guidance
│   ├── Exercise & Fitness Tips
│   └── Mental Wellness
├── 3. Common Medicine Suggestions
├── 4. First Aid Information
│   ├── First Aid Guidance
│   └── Emergency Contacts
└── 5. Exit System
⚠️ Important Disclaimer
This application provides general health information only. It is NOT a substitute for professional medical advice, diagnosis, or treatment. Always seek the advice of your physician or other qualified health provider with any questions you may have regarding a medical condition. For emergencies, call your local emergency number immediately.

🧪 Academic Value
This project is excellent for learning:

Python decorators in practical applications

Design patterns for menu systems and service registration

Clean architecture with separation of concerns

Frontend-backend integration concepts

🔧 Customization
Adding New Services
python
@virtual_doctor_service("Your Service Name", menu="main", requires_input=True)
def your_service_function(user_input):
    """Your service description"""
    # Your logic here
    return "Service result"
Modifying Menus
Change the menu parameter to place services in different menus

Update requires_input based on whether the service needs user input

Modify service descriptions for better user experience

📚 Learning Points
Decorator Patterns: How to use decorators for registration and configuration

Dynamic Dispatch: Routing user selections to appropriate functions

Menu Management: Building hierarchical menus without hardcoded logic

Input Validation: Handling user input safely and consistently

State Management: Managing application state across multiple menus

🤝 Contributing
While this is primarily an academic project, suggestions are welcome:

Fork the repository

Create a feature branch

Commit your changes

Push to the branch

Open a Pull Request

📄 License
This project is created for educational purposes. Feel free to use and modify for learning and academic projects.

👨‍⚕️ Author
Muhammad Danish Wahab
Gmail:
danishwahabkhan.1@gmail.com
Created for demonstrating advanced Python decorator patterns in a practical, real-world application scenario.

Remember: This is an educational tool. For real medical concerns, always consult healthcare professionals
