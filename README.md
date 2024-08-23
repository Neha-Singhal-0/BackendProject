# Media Upload Backend Project

A backend project designed to handle image and video uploads with support for both Cloudinary and local storage options. This project uses MongoDB Atlas for data management and sends email notifications to users via Gmail using Nodemailer. The project is structured following the MVC (Model-View-Controller) pattern and is tested using Postman.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Testing](#testing)
- [Project Structure](#project-structure)


## Overview

This project provides a robust backend solution for uploading images and videos. Users can choose between uploading media files to Cloudinary or storing them locally. Upon successful upload, an email notification is sent to the user's Gmail account using Nodemailer. The project does not include a frontend and was tested using Postman.

## Features

- **Image and Video Upload**: Supports uploading media files to Cloudinary or local storage.
- **Email Notifications**: Sends an email to the user's Gmail account upon successful upload.
- **Data Management**: Uses MongoDB Atlas for storing metadata related to uploaded files.
- **MVC Structure**: Organized following the Model-View-Controller pattern for maintainability.

## Technologies Used

- **Node.js**: JavaScript runtime for building the server-side application.
- **Express.js**: Web framework for Node.js.
- **MongoDB Atlas**: NoSQL database for storing file metadata.
- **Mongoose**: Object Data Modeling (ODM) library for MongoDB and Node.js.
- **Cloudinary**: Cloud service for storing and managing images and videos.
- **Nodemailer**: Library for sending emails via SMTP.
- **dotenv**: Module to manage environment variables.

## Installation

1. Clone the repository to your local machine:

    ```bash
    git clone https://github.com/yourusername/media-upload-backend.git
    ```

2. Navigate to the project directory:

    ```bash
    cd media-upload-backend
    ```

3. Install the necessary dependencies:

    ```bash
    npm install
    ```

4. Set up your environment variables:

    - Create a `.env` file in the root of your project and add your configurations:

      ```env
      CLOUDINARY_CLOUD_NAME=yourCloudinaryCloudName
      CLOUDINARY_API_KEY=yourCloudinaryApiKey
      CLOUDINARY_API_SECRET=yourCloudinaryApiSecret
      MONGODB_URI=yourMongoDbUri
      EMAIL_SERVICE=gmail
      EMAIL_USER=yourGmailAddress
      EMAIL_PASS=yourGmailPassword
      ```

5. Start the application:

    ```bash
    npm start
    ```

## Usage

- **Upload Media**: Use Postman to send POST requests to the API endpoints for uploading images and videos.
- **Email Notifications**: Upon successful upload, the user receives an email notification.
- **View Uploaded Media**: Access the uploaded files via the Cloudinary link or the local file path stored in MongoDB Atlas.
  
## Testing
Postman: Use Postman to test the API endpoints by sending different requests for uploading media files.

## Project Structure

```plaintext
BackendProject/
│
├── controllers/
│   └── fileUpload.js   # Handles the logic for media upload and email notifications
│   └── files/  # For local storage 
│
├── models/
│   └── File.js        # Mongoose schema and model for storing media file metadata
│
├── routes/
│   └── FileUpload.js       # Routes for handling media-related requests
│
├── config/
│   └── database.js      # Service for sending email notifications using Nodemailer
│   └── cloudinary.js # Service for interacting with Cloudinary API
│
├── .env                     # Environment variables
├── app.js                   # Main application file
├── package.json             # Project metadata and dependencies
└── README.md                # Project documentation
