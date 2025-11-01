# Goal: Build a simple app to manage books in a library.
Features:
- Add new books
- View all books
- Search by author or title
- Update book info
- Delete books

## ✅ 1. Django Model – models.py
- This defines the structure of the data (like a table in the database).
- **models** are blueprints for the database.
- **Model** is a class provided by Django that you inherit from when you want to define a database table.

### library/models.py

from django.db import models

class Book(models.Model):
    title = models.CharField(max_length=100)
    author = models.CharField(max_length=100)
    published_date = models.DateField()

    def __str__(self):
        return f"{self.title} by {self.author}"

## 🔄 2. Django ORM – Using Python to interact with the database
- **Object Relational Mapping** - tool that lets you talk to your database using python code instead of writing SQL
- **objects** default manager that Django automatically attaches to every model class defined.

### Create a book
Book.objects.create(title="Django for Beginners", author="Irene", published_date="2025-11-01")

### Get all books
books = Book.objects.all()

### Filter books by author
books_by_irene = Book.objects.filter(author="Irene")

### Update a book
book = Book.objects.get(id=1)
book.title = "Django Advanced"
book.save()

### Delete a book
book.delete()

## ⚙️ 3. Settings & MySQL Configuration (settings.py)

pip install mysqlclient


#### Then configure the database:--> project/settings.py

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'library_db',
        'USER': 'your_mysql_user',
        'PASSWORD': 'your_mysql_password',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}

## 🧱 4. Migrations – Creating tables from models

python manage.py makemigrations
python manage.py migrate

## 🌐 5. Views – views.py
This handles logic for displaying or processing data

### library/views.py

from django.shortcuts import render, redirect
from .models import Book

def book_list(request):
    books = Book.objects.all()
    return render(request, 'book_list.html', {'books': books})

def add_book(request):
    if request.method == 'POST':
        title = request.POST['title']
        author = request.POST['author']
        published_date = request.POST['published_date']
        Book.objects.create(title=title, author=author, published_date=published_date)
        return redirect('book_list')
    return render(request, 'add_book.html')

## 6. 🖼️ Templates
