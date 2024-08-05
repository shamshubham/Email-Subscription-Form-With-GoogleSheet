# Subscribe Form to Google Sheet

This project demonstrates how to create a subscription form that sends user email addresses to a Google Sheet using Google Apps Script. The form is designed to collect email addresses and provide feedback to the user upon submission.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Code Overview](#code-overview)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Introduction

The "Subscribe Form to Google Sheet" project allows users to enter their email addresses into a form, which is then submitted to a Google Sheet. The form provides a user-friendly interface and immediate feedback upon successful submission.

## Features

- **Email Subscription Form**: Collects user email addresses.
- **Google Sheets Integration**: Submits data to a Google Sheet using Google Apps Script.
- **User Feedback**: Displays a thank you message upon successful submission.

## Technologies Used

- **HTML5**: Provides the structure of the web page.
- **CSS3**: Used for styling the page (assumed to be in a `style.css` file).
- **JavaScript**: Handles form submission and interaction with the Google Apps Script.
- **Google Apps Script**: Used to connect the form to a Google Sheet.

## Getting Started

### Prerequisites

- A Google account to create and use Google Sheets and Google Apps Script.
- Basic knowledge of HTML, CSS, and JavaScript.

### Setup Google Sheets and Apps Script

1. **Create a Google Sheet**:

   - Go to [Google Sheets](https://sheets.google.com) and create a new spreadsheet.
   - Note the spreadsheet ID from the URL, as you will need it for the Google Apps Script.

2. **Create a Google Apps Script**:

   - Go to [Google Apps Script](https://script.google.com) and create a new project.
   - Replace the default script with the following code to handle form submissions:

   ```javascript
   function doPost(e) {
     var sheet = SpreadsheetApp.openById("YOUR_SPREADSHEET_ID").getSheetByName(
       "Sheet1"
     );
     var data = e.parameter;
     sheet.appendRow([new Date(), data.Email]);
     return ContentService.createTextOutput("Success");
   }
   ```

   - Replace `'YOUR_SPREADSHEET_ID'` with your actual Google Sheet ID.
   - Save and deploy the script as a web app, making sure to set the access level to "Anyone" or "Anyone, even anonymous".

3. **Copy the Web App URL**:

   - This URL will be used as `scriptURL` in your JavaScript code.

### Installation

1. **Clone the Repository**:

   ```bash
   git clone <repository-url>
   cd subscribe-form-to-google-sheet
   ```

2. **Open the Project**:

   Open the `index.html` file in your web browser to view and interact with the application.

## Usage

1. **Open the Application**:

   Open `index.html` in a web browser.

2. **Enter Email Address**:

   Type your email address into the input field.

3. **Submit the Form**:

   Click the submit button to send your email address to the Google Sheet.

4. **View Feedback**:

   After submission, a thank you message will be displayed.

## Contributing

Contributions are welcome! If you have any enhancements or bug fixes, please fork the repository and create a pull request. For major changes, please discuss them via issues first.

## License

This project is open-source and available under the MIT License.

## Acknowledgments

Thanks to Google for providing the Google Sheets and Apps Script services for this integration.
