## Task Description:
Install Django and create a new Django project named LibraryProject. This initial setup will serve as the foundation for developing Django applications. You’ll also explore the project’s default structure to understand the roles of various components.

### Steps:
1) Install Django:

- Ensure Python is installed on your system.
- Install Django using pip: pip install django.
2) Create Your Django Project:

- Create a new Django project by running: django-admin startproject LibraryProject.
3) Run the Development Server:

- Navigate into your project directory (cd LibraryProject).
- Create a README.md file inside the LibraryProject.
- Start the development server using: python manage.py runserver.
- Open a web browser and go to http://127.0.0.1:8000/ to view the default Django welcome page.

############################################################################################################################################################################
2
########################################################################################################################################################################

## Implementing and Interacting with Django Models

### Objective: Demonstrate proficiency in Django by creating a Book model within a Django app, implementing it according to specified attributes, and using Django’s ORM to perform database operations.

### Task Description:
For this task, you will develop a Django app named bookshelf within your existing Django project. You will define a Book model with specific attributes and demonstrate basic CRUD operations through the Django shell. This task is structured to ensure consistent implementations suitable for automated checking.

## Steps:
### 1. Create the bookshelf App:

In your Django project directory, use Django’s command-line utility to generate a new app: python manage.py startapp bookshelf.
### 2. Define the Book Model:

- Navigate to bookshelf/models.py.
- Create a Book class with the following fields:
--- title: CharField with a maximum length of 200 characters.
--- author: CharField with a maximum length of 100 characters.
--- publication_year: IntegerField.
  Ensure the model is correctly set up for migrations.

### 1. Model Migration:

- Prepare your model for database integration by running python manage.py makemigrations bookshelf to create migration files.
- Apply migrations to update the database with python manage.py migrate.
### 2. Interact with the Model via Django Shell:
Open the Django shell with python manage.py shell and execute CRUD operations:
- Create a Book instance.
- Retrieve the book you created.
- Update the title of the created book.
- Delete the book instance.
Perform Specific CRUD Operations in the Django Shell: - Document each operation in separate Markdown files (create.md, retrieve.md, update.md, delete.md) detailing both the Python command used and its output.

### Detailed CRUD Operations and Documentation:
a) Create:

- Command: Create a Book instance with the title “1984”, author “George Orwell”, and publication year 1949.
- Document in: create.md
- Expected Documentation: Include the Python command and a comment with the expected output noting the successful creation.
b) Retrieve:

- Command: Retrieve and display all attributes of the book you just created.
- Document in: retrieve.md
- Expected Documentation: Include the Python command and a comment with the expected output showing the details of the book.
c) Update:

- Command: Update the title of “1984” to “Nineteen Eighty-Four” and save the changes.
- Document in: update.md
- Expected Documentation: Include the Python command and a comment with the expected output showing the updated title.
d) Delete:

- Command: Delete the book you created and confirm the deletion by trying to retrieve all books again.
- Document in: delete.md
- Expected Documentation: Include the Python command and a comment with the expected output confirming the deletion.

### Implementation and Submission Instructions:
- Code Implementation: Your models.py file should correctly define the Book model as specified. Ensure that all field types and options are accurately implemented.
- Database Operations: Perform and document each CRUD operation in the Django shell. Save your commands and their outputs in a file named CRUD_operations.md.


############################################################################################################################################################################
3
########################################################################################################################################################################
