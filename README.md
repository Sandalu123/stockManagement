# Task Document: Building a Stock Management System

## Introduction

Welcome to your first project as a .NET intern software developer! In this task, you will build a Stock Management System using .NET 8, C#, MySQL, HTML, and CSS with Bootstrap. This project will help you understand the fundamentals of web development, database management, and user authentication.

### Project Overview

The Stock Management System will allow users to:

- **Create an account** (Sign up) and **log in**.
- **Add**, **update**, **delete**, and **view** products.
- **Manage stock levels** for each product.

### Technologies You'll Use

- **.NET 8 (C#)**: For backend development.
- **MySQL**: For the database.
- **HTML, CSS, Bootstrap**: For frontend development.

---

## Task Breakdown

Follow the steps below to complete the project. Each step includes guidance to help you understand what needs to be done.

### 1. Set Up Your Development Environment

**Objective**: Install all the necessary tools to start developing.

#### Steps:

- **Install .NET 8 SDK**:
  - Download the .NET 8 SDK from the [official website](https://dotnet.microsoft.com/download).
- **Choose an IDE**:
  - **Visual Studio 2022** (Recommended for Windows users).
  - **Visual Studio Code** (Cross-platform).
- **Install MySQL**:
  - Download and install **MySQL Community Server** and **MySQL Workbench** from the [MySQL website](https://dev.mysql.com/downloads/).
- **Install Git**:
  - For version control, install Git from the [official site](https://git-scm.com/downloads).

---

### 2. Create a New ASP.NET Core Web Application

**Objective**: Set up the initial web application project.

#### Steps:

- **Open your IDE**:
  - Launch Visual Studio or Visual Studio Code.
- **Create a New Project**:
  - Select **ASP.NET Core Web App**.
- **Configure the Project**:
  - **Project Name**: `StockManagementSystem`.
  - **Framework**: Choose **.NET 8**.
- **Project Template**:
  - Choose **MVC (Model-View-Controller)** for project structure.

---

### 3. Set Up the Database

**Objective**: Create a MySQL database and set up the connection.

#### Steps:

- **Create a New Database**:
  - Open **MySQL Workbench**.
  - Create a database named `stock_management`.
- **Design the Database Schema**:
  - **Tables to Create**:
    - `Users`: `UserId`, `Username`, `PasswordHash`, `Email`.
    - `Products`: `ProductId`, `ProductName`, `Description`, `Price`.
    - `Stocks`: `StockId`, `ProductId`, `Quantity`.
- **Install Entity Framework Core**:
  - Use NuGet Package Manager to install:
    - `Microsoft.EntityFrameworkCore`.
    - `Microsoft.EntityFrameworkCore.MySQL` (or `Pomelo.EntityFrameworkCore.MySql`).
- **Configure the Connection String**:
  - In `appsettings.json`, add the connection string to your MySQL database.

---

### 4. Implement User Account Management

**Objective**: Allow users to sign up and log in.

#### Steps:

- **Set Up ASP.NET Identity**:
  - Install `Microsoft.AspNetCore.Identity.EntityFrameworkCore` via NuGet.
- **Configure Identity in Startup.cs**:
  - Add Identity services in the `ConfigureServices` method.
- **Create User Models and Context**:
  - Create a `User` model that extends `IdentityUser`.
  - Update your `DbContext` to include Identity.
- **Create Registration and Login Views**:
  - **Registration**:
    - Fields: Username, Email, Password, Confirm Password.
  - **Login**:
    - Fields: Username/Email, Password.
- **Handle Authentication**:
  - Use Identity's built-in methods to handle user creation and sign-in.

---

### 5. Build Product Management Features

**Objective**: Implement CRUD operations for products.

#### Steps:

- **Create Product Model**:
  - Define properties: `ProductId`, `ProductName`, `Description`, `Price`.
- **Update DbContext**:
  - Add `DbSet<Product>` to your context.
- **Create Product Controller**:
  - Actions:
    - `Index`: List all products.
    - `Create`: Add a new product.
    - `Edit`: Update an existing product.
    - `Delete`: Remove a product.
- **Create Views for Each Action**:
  - Use Razor Views to create forms and display data.
- **Implement Validation**:
  - Use Data Annotations to ensure required fields are filled out.

---

### 6. Implement Stock Management

**Objective**: Manage stock levels for each product.

#### Steps:

- **Create Stock Model**:
  - Define properties: `StockId`, `ProductId`, `Quantity`.
- **Update DbContext**:
  - Add `DbSet<Stock>` to your context.
- **Establish Relationships**:
  - Configure one-to-many relationship between `Product` and `Stock`.
- **Create Stock Controller**:
  - Actions similar to the Product Controller.
- **Create Views for Stock Management**:
  - Forms to add, update, and delete stock entries.
- **Display Stock Information**:
  - On the product details page, show current stock levels.

---

### 7. Design the User Interface with Bootstrap

**Objective**: Create a responsive and user-friendly interface.

#### Steps:

- **Include Bootstrap in Your Project**:
  - Use CDN links or install via npm.
- **Layout View**:
  - Modify `_Layout.cshtml` to include navigation menus.
- **Styling**:
  - Use Bootstrap classes to style forms, buttons, tables, and navigation.
- **Responsive Design**:
  - Ensure the site looks good on different screen sizes.

---

### 8. Implement Authorization

**Objective**: Restrict certain actions to authenticated users.

#### Steps:

- **Protect Controllers**:
  - Use `[Authorize]` attribute on controllers or actions that require login.
- **Redirect Unauthenticated Users**:
  - Configure the app to redirect unauthenticated users to the login page.
- **Role-Based Access (Optional)**:
  - Implement roles like Admin and User for more granular control.

---

### 9. Test the Application

**Objective**: Ensure all features work as intended.

#### Steps:

- **Test User Registration and Login**:
  - Create a new account and log in.
- **Test Product Management**:
  - Add, edit, and delete products.
- **Test Stock Management**:
  - Update stock levels and verify changes.
- **Test Validation**:
  - Try submitting forms without required fields to ensure validation works.
- **Cross-Browser Testing**:
  - Test the application in different web browsers.

---

### 10. Deploy the Application Locally

**Objective**: Run the application outside of the development environment.

#### Steps:

- **Publish the Application**:
  - Use the publish feature in your IDE to compile the application.
- **Configure IIS (Windows)**:
  - Set up a local IIS server and deploy the application.
- **Run the Application**:
  - Access the application via a web browser using `http://localhost/yourapp`.

---

### 11. Document Your Work

**Objective**: Create documentation for future reference.

#### Steps:

- **Code Comments**:
  - Add comments to your code to explain functionality.
- **README File**:
  - Write a README that includes:
    - Project overview.
    - Setup instructions.
    - How to use the application.
- **User Guide**:
  - Create a simple guide on how to navigate and use the system.

---

## Additional Tips

- **Break Down Tasks**: Tackle one feature at a time to avoid feeling overwhelmed.
- **Ask Questions**: If you're unsure about something, don't hesitate to seek guidance.
- **Version Control**: Regularly commit your code changes using Git.
- **Stay Organized**: Keep your files and folders structured logically.

---

## Learning Resources

- **Microsoft Docs**:
  - [ASP.NET Core Tutorials](https://docs.microsoft.com/en-us/aspnet/core)
- **Entity Framework Core**:
  - [Getting Started with EF Core](https://docs.microsoft.com/en-us/ef/core/get-started/)
- **Bootstrap Documentation**:
  - [Bootstrap 5 Docs](https://getbootstrap.com/docs/5.0/getting-started/introduction/)
- **MySQL Documentation**:
  - [MySQL Workbench Manual](https://dev.mysql.com/doc/workbench/en/)

---

## Deliverables

- A fully functional Stock Management System.
- Source code hosted in a Git repository.
- Documentation including a README and a user guide.

---

Good luck with your project! Remember, the goal is to learn and understand each part of the development process.
