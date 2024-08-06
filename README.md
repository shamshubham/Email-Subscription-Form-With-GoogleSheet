# 📬 Subscribe Form to Google Sheet

Welcome to the **Subscribe Form to Google Sheet** project! This tool seamlessly integrates a subscription form with Google Sheets, allowing users to submit their email addresses directly to a spreadsheet. The form provides instant feedback, making it easy and efficient to manage email subscriptions.

## 📚 Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## 🌟 Introduction

The "Subscribe Form to Google Sheet" project facilitates the collection of user email addresses through a web-based form. By leveraging Google Apps Script, the form ensures that submissions are automatically recorded in a Google Sheet, providing real-time user feedback.

![Subscribe Form Example](https://github.com/shamshubham/Email-Subscription-Form-With-GoogleSheet/blob/master/screenShots/Capture.JPG)

## ✨ Features

- **Email Subscription Form**: Collects and submits user email addresses.
- **Google Sheets Integration**: Directly sends data to a Google Sheet via Google Apps Script.
- **Instant Feedback**: Displays a confirmation message upon successful submission.

## 💻 Technologies Used

- **HTML5**: Structures the web page.
- **CSS3**: Styles the form and feedback messages (assumed to be in `style.css`).
- **JavaScript**: Manages form submissions and interacts with Google Apps Script.
- **Google Apps Script**: Facilitates data submission to Google Sheets.

## 🚀 Getting Started

### Prerequisites

- A Google account to access Google Sheets and Google Apps Script.
- Basic knowledge of HTML, CSS, and JavaScript.

### Setup Google Sheets and Apps Script

1. **Create a Google Sheet**:

   - Navigate to [Google Sheets](https://sheets.google.com) and create a new spreadsheet.
   - Copy the spreadsheet ID from the URL; you'll need this for the Google Apps Script.

2. **Create a Google Apps Script**:

   - Visit [Google Apps Script](https://script.google.com) and create a new project.
   - Replace the default script with the following code:

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
   - Save and deploy the script as a web app, setting access to "Anyone" or "Anyone, even anonymous."

3. **Copy the Web App URL**:
   - Use this URL as `scriptURL` in your JavaScript code.

### Installation

1. **Clone the Repository**:

   ```bash
   git clone <repository-url>
   cd subscribe-form-to-google-sheet
   ```

2. **Open the Project**:
   - Launch the `index.html` file in your web browser to interact with the subscription form.

## 🛠️ Usage

1. **Open the Application**:

   - Open `index.html` in a web browser.

2. **Enter Email Address**:

   - Input your email address into the form field.

3. **Submit the Form**:

   - Click the submit button to send your email address to the Google Sheet.

4. **View Feedback**:
   - After submission, you'll see a thank you message confirming the successful submission.

## 🤝 Contributing

We welcome contributions to enhance this project! To contribute:

1. **Fork the Repository**: Create a personal copy on GitHub.
2. **Create a Feature Branch**: Develop your changes in a new branch.
3. **Commit Changes**: Add and commit your modifications.
4. **Push to the Branch**: Push changes to your forked repository.
5. **Create a Pull Request**: Submit a pull request to propose your changes.

For major updates, please open an issue to discuss them first.

## 📜 License

This project is open-source and licensed under the [MIT License](LICENSE). Feel free to use, modify, and distribute the code.

## 🙏 Acknowledgments

A special thanks to Google for providing the tools that make this integration possible and to the web development community for their support and resources.
