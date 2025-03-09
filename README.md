# Library-Management-System-CS253 Assignment
Overview
This project implements a Library Management System (LMS) using Object-Oriented Programming (OOP) concepts in C++. The system demonstrates the principles of encapsulation, inheritance, abstraction, and polymorphism. It provides functionality for different user roles including Students, Faculty, and Librarians.

Features
User Roles and Permissions:

Students:
Can borrow up to 3 books at a time.
Maximum borrowing period: 15 days.
Fine: 10 rupees per day for overdue books.
Cannot manage books or other users.
Faculty:
Can borrow up to 5 books at a time.
Maximum borrowing period: 30 days.
No fine is applied for overdue books.
Cannot borrow additional books if they have an overdue book for more than 60 days.
Cannot manage books or other users.
Librarians:
Can manage the library including adding, removing, and updating books.
Can add or remove user accounts.
Do not borrow books.
Book Management:

Books have attributes such as title, author, publisher, year, ISBN, and status.
The status of a book is updated upon borrowing or returning.
The system maintains file-based persistence for books.
Account Management:

Each user has an associated account that tracks:
Currently borrowed books.
Borrowing history.
Outstanding fines.
Returning and Updating Rules:

Upon returning a book, the system checks if it is overdue.
For students, overdue fine is calculated as (Days Overdue × 10 rupees).
For faculty, no fine is applied.
The book’s status is updated to “Available” and the book is added to the user’s borrowing history.
Users with outstanding fines cannot borrow additional books.
Login/Logout Mechanism:

Users log in using their User ID.
Role-specific menus are provided.
Users can log out to return to the login prompt.
File Persistence:

Data is stored in files for both books and users.
On startup, data is loaded from files.
Upon exit, data is saved to ensure persistence between sessions.
Files in the Repository
main.cpp
Contains the complete C++ code for the Library Management System.

books.txt
A sample file containing initial book records in CSV format.

users.txt
A sample file containing initial user records in CSV format.

README.md
This file.

How to Compile and Run
Compilation:
Use a C++ compiler such as g++. For example, compile the code with:

bash
Copy
g++ main.cpp -o LMS
Running the Application:
Execute the generated executable:

bash
Copy
./LMS
The program will load existing data (if available) from books.txt and users.txt, or initialize with default data.

Using the Application:

Login:
Enter your User ID to log in. For example, use IDs such as 101 for a student, 201 for a faculty member, or 301 for a librarian.
Menu Options:
Based on your role, you will be presented with options to borrow/return books, pay fines, manage books, and more.
Logout:
Select the logout option from the menu to return to the login prompt.
Project Structure and Design
OOP Principles:
The project is designed using object-oriented principles:

Encapsulation:
All class attributes are private and are accessed via public methods.
Inheritance:
The User base class is inherited by Student, Faculty, and Librarian classes.
Polymorphism:
Virtual methods such as borrowBook() and returnBook() are overridden by derived classes to enforce role-specific behavior.
Abstraction:
The main interface and file operations hide implementation details from the user.
File-Based Persistence:
The system reads from and writes to files (books.txt and users.txt) to persist data between sessions.

Known Limitations
The current system uses a simple file-based CSV format for persistence. In a production system, you might consider using a database.
The date for return is determined automatically using system time. For a more interactive system, the interface can be modified to allow user input for return dates.
Error handling is minimal. Additional checks and validations may be required for robust error handling in production code.
Conclusion
This project is a demonstration of implementing a Library Management System using C++ and OOP concepts. It covers essential operations such as borrowing, returning, fine calculation, and account management while providing file-based persistence.

Feel free to customize this README file further based on any additional requirements or features added to your project.






You said:
non plagiarize this readme fike
Reasoned for a second
Library Management System (LMS) in C++
Project Summary
This project implements a Library Management System (LMS) using C++ with a strong focus on Object-Oriented Programming (OOP) principles. It demonstrates key concepts such as encapsulation, inheritance, polymorphism, and abstraction, while providing role-based functionality for students, faculty, and librarians.

Key Features
Role-Based Functionality:

Students:
Allowed to borrow up to 3 books concurrently.
Borrowing period: 15 days.
Overdue fine: 10 rupees per day.
No permissions for system management.
Faculty:
Can borrow up to 5 books concurrently.
Borrowing period: 30 days.
No overdue fine is applied.
Additional borrowing is restricted if any book is overdue by more than 60 days.
Librarians:
Responsible for managing the library system, including adding or removing books and users.
Do not have borrowing privileges.
Book Management:

Each book is defined by attributes such as title, author, publisher, year, ISBN, and status.
The system updates the status of books upon borrowing or return.
Account Management:

Every user has an associated account that maintains:
A record of currently borrowed books.
A history of returned books.
The amount of any outstanding fines.
Return Process and Fine Calculation:

When a book is returned, its status is set to "Available".
For students, if a book is returned after the allowed period, the system computes the overdue period and applies a fine at 10 rupees per day.
Faculty members do not incur fines; however, borrowing is denied if any borrowed book is overdue by more than 60 days.
Returned books are removed from the active borrow list and added to the borrowing history.
User Authentication:

The system includes a login and logout mechanism where users enter their User ID to access role-specific options.
Data is persisted in files, ensuring that the library’s state is maintained between sessions.
Repository Contents
main.cpp
Contains the full C++ source code implementing the LMS.

books.txt
A sample file with initial book data in CSV format.

users.txt
A sample file with initial user data in CSV format.

README.md
This documentation file.

Building and Running the Application
Compilation:

Use a C++ compiler (for instance, g++) to compile the project:
bash
Copy
g++ main.cpp -o LMS
Execution:

Run the compiled executable:
bash
Copy
./LMS
The program loads data from the CSV files if available; otherwise, it initializes with default data.
Usage:

Login:
Users enter their User ID to access the system. For instance, student IDs (e.g., 101), faculty IDs (e.g., 201), or librarian IDs (e.g., 301) may be used.
Operations:
After logging in, a menu is presented with options tailored to the user’s role. Options include borrowing or returning books, paying fines, and managing library data (for librarians).
Logout:
Users may log out to return to the main login prompt.
Design Considerations
OOP Principles:

Encapsulation:
All data members are private and accessed through public member functions.
Inheritance:
A common User base class is extended by Student, Faculty, and Librarian classes to differentiate behavior.
Polymorphism:
Virtual functions (e.g., borrowBook() and returnBook()) allow derived classes to implement role-specific functionality.
Abstraction:
The user interface and file handling operations abstract away the implementation details from the end user.
Data Persistence:

The system uses file-based persistence to store and retrieve data, ensuring that the library’s state is maintained across different sessions.
Limitations and Future Enhancements
File Format:
Data is stored using a basic CSV format. Future versions may benefit from more robust data storage solutions such as databases.
User Input for Dates:
Currently, the system uses the system’s current date for borrowing and return operations. Future enhancements could allow manual entry of return dates.
Error Handling:
While basic error handling is implemented, additional validations and exception management could be introduced for improved robustness.
