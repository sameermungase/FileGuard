# FileGuard

## Overview
This project is a Java application for managing hidden files. It includes functionalities for user registration and login, sending OTPs (One-Time Passwords) for authentication, and hiding/unhiding files associated with a user.

## Features
- **User Management**: Users can sign up and log in using their email. OTPs are generated and sent via email for authentication.
- **File Management**: Users can hide files by storing their metadata and content in a database and unhide them later.
- **Database Interaction**: The project uses MySQL for storing user and file data.

## Build and Run
### Prerequisites
- Java 17
- Maven
- MySQL

### Setup
1. Clone the repository:
    ```sh
    git clone <repository-url>
    ```

2. Configure the MySQL database:
    - Create a database named `FileGuard`.
    - Update the database connection details in [MyConnection].

3. Build the project using Maven:
    ```sh
    mvn clean install
    ```

4. Run the application:
    ```sh
    java -cp target/ytproject-1.0-SNAPSHOT.jar Main
    ```

## Project Structure
- **Main Class**: The entry point of the application is the [Main](http://_vscodecontentref_/2) class.
- **Views**: User interface components are in the [views](http://_vscodecontentref_/3) package.
  - [Welcome](http://_vscodecontentref_/4): Handles user login and signup.
  - [UserView](http://_vscodecontentref_/5): Provides options for hiding and unhiding files.
- **Services**: Business logic and utility functions are in the [service](http://_vscodecontentref_/6) package.
  - [GenerateOTP](http://_vscodecontentref_/7): Generates OTPs.
  - [SendOTPService](http://_vscodecontentref_/8): Sends OTPs via email.
  - [UserService](http://_vscodecontentref_/9): Manages user-related operations.
- **Data Access Objects (DAO)**: Database interaction logic is in the [dao](http://_vscodecontentref_/10) package.
  - [UserDAO](http://_vscodecontentref_/11): Manages user data.
  - [DataDAO](http://_vscodecontentref_/12): Manages file data.
- **Models**: Data models are in the [model](http://_vscodecontentref_/13) package.
  - [User](http://_vscodecontentref_/14): Represents a user.
  - [Data](http://_vscodecontentref_/15): Represents a file.

## Functions
### User Management
- **Sign Up**: Users can sign up by providing their name and email. An OTP is sent to their email for verification.
- **Login**: Users can log in by providing their email. An OTP is sent to their email for verification.

### File Management
- **Hide File**: Users can hide a file by providing its path. The file's metadata and content are stored in the database.
- **Unhide File**: Users can unhide a file by selecting it from the list of hidden files. The file is restored to its original path.

## Database Schema
- **Users Table**: Stores user information.
  - [id](http://_vscodecontentref_/16) (INT): Primary key.
  - [name](http://_vscodecontentref_/17) (VARCHAR): User's name.
  - [email](http://_vscodecontentref_/18) (VARCHAR): User's email.
- **Data Table**: Stores file information.
  - [id](http://_vscodecontentref_/19) (INT): Primary key.
  - [name](http://_vscodecontentref_/20) (VARCHAR): File name.
  - [path](http://_vscodecontentref_/21) (VARCHAR): File path.
  - [email](http://_vscodecontentref_/22) (VARCHAR): User's email.
  - [bin_data](http://_vscodecontentref_/23) (CLOB): File content.
