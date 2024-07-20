# Online Chat Application

This is an online chat application built using Python and a SQL Server database. It allows users to connect to a central server, chat with other users, and view the chat history.

## Table of Contents
- [Introduction](#introduction)
- [Installation and Setup](#installation-and-setup)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Database Schema](#database-schema)
- [Contributing](#contributing)
- [License](#license)

## Introduction

The Online Chat Application is a simple yet powerful chat platform that enables users to communicate with each other in real-time. It features user authentication, online status tracking, and a chat history viewer. The application is built using Python and a SQL Server database to store user information and chat messages.

## Installation and Setup

1. Clone the repository:
   ```
   git clone https://github.com/fatemehRamazanain/online-chatapp.git
   ```
2. Install the required dependencies:
   ```
   cd online-chat-app
   pip install -r requirements.txt
   ```
3. Set up the SQL Server database:
   - Create a new database.
   - Run the SQL script provided in the `database_table.sql` file to create the necessary tables.
   - Update the database connection details in the `database.py` file.

4. Start the server:
   ```
   python server.py
   ```

## Usage

1. Run the `main.py` file to start the client application.
2. Register a new user or log in with an existing account.
3. The chat page will be displayed, showing a list of online users.
4. Select a user from the list to start a conversation.
5. Type your message in the input field and click "Send" to send it.
6. The chat history will be displayed in the chat window.
7. To logout, click the "Logout" button.

## Project Structure

The project consists of the following files:

- `chat_page.py`: Implements the chat page UI and functionality, including sending and receiving messages, updating the online status, and loading the chat history.
- `client.py`: Handles the client-side functionality, such as connecting to the server and managing the chat session.
- `database.py`: Provides functions to interact with the SQL Server database, including getting other users, sending messages, and loading the chat history.
- `login.py`: Implements the login page UI and functionality, allowing users to authenticate with the application.
- `main.py`: Serves as the entry point for the client application, managing the different pages and state.
- `register.py`: Implements the registration page UI and functionality, allowing users to create new accounts.
- `server.py`: Implements the server-side functionality, including managing client connections and relaying messages between clients.
- `database_table.sql`: Contains the SQL script to create the necessary database tables.

## Database Schema

The application uses a SQL Server database with the following schema:

1. **Users** table:
   - `UserID`: Unique identifier for the user (primary key)
   - `Username`: Username of the user (unique)
   - `Password`: Hashed password of the user
   - `IsOnline`: Indicates whether the user is currently online

2. **Messages** table:
   - `MessageID`: Unique identifier for the message (primary key)
   - `SenderID`: Foreign key reference to the `UserID` of the sender
   - `ReceiverID`: Foreign key reference to the `UserID` of the receiver
   - `Content`: The content of the message
   - `Timestamp`: The timestamp when the message was sent
   - `IsRead`: Indicates whether the message has been read by the receiver

## Contributing

If you would like to contribute to this project, please follow these guidelines:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and test them thoroughly.
4. Submit a pull request with a detailed description of your changes.

All contributions are welcome, and they will be reviewed and merged if they align with the project's goals and standards.

## License

This project is licensed under the [MIT License](LICENSE).
