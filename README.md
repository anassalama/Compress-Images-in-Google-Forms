# Compress Images in Google Forms

## 📚 Overview
This Google Apps Script project automates the compression of image files uploaded via Google Forms. It processes the images, reduces their size, and optionally sends them via email to the form respondents.

## 🚀 Features
- Compress images uploaded via Google Forms submissions.
- Store compressed images in Google Drive.
- Send compressed images to respondents via email.
- Dynamic configuration through a Google Sheets "Settings" sheet.
- Automated triggers for seamless integration with form submissions.

## 📂 Project Structure

- **util.js**
   - `compressImageFile_`: Compresses an image file to a given size.
   - `getSettings_`: Fetches settings from a Google Sheets tab.
   - `parseNamedValues_`: Parses named values from form submissions.
   - `updateRowValues_`: Updates form submission rows with new data.
   - `sendImage_`: Sends compressed images via Gmail.

- **code.js**
   - `installTrigger`: Installs a trigger for form submissions.
   - `uninstallTrigger`: Removes triggers from the project.
   - `onOpen`: Adds a custom menu for trigger management.
   - `triggerOnFormSubmit`: Handles the image compression workflow when a form is submitted.

## ⚙️ Setup Instructions

1. Open your Google Spreadsheet associated with the Google Form.
2. Navigate to **Extensions > Apps Script**.
3. Copy and paste the contents of `util.js` and `code.js` into the Apps Script editor.
4. Create a sheet named `Settings` in your Google Spreadsheet and add the following columns:
   - `imageField` (Field name for the image upload)
   - `emailField` (Field name for respondent email)
   - `emailImage` (`TRUE` or `FALSE` to enable/disable email functionality)
   - `size` (Desired image width, e.g., `800`)
   - `errorHeader` (Header for error logging)
   - `imageHeader` (Header for storing compressed image URLs)
5. Save the script and run the `installTrigger` function.

## 📧 Permissions
The script requires the following permissions:
- Access Google Drive files
- Send emails via Gmail
- Manage spreadsheet data

## 🛠️ How It Works
1. A respondent uploads an image via Google Forms.
2. The `triggerOnFormSubmit` function compresses the uploaded image.
3. The compressed image is saved in Google Drive.
4. (Optional) The compressed image is emailed to the respondent.
5. The submission row in Google Sheets is updated with relevant information.

## 📝 Configuration Example
In the `Settings` sheet:
| imageField  | emailField  | emailImage | size | errorHeader | imageHeader |
|-------------|-------------|------------|------|-------------|-------------|
| ImageUpload | Email       | TRUE       | 800  | Status      | CompressedURL |

## 🧑‍💻 Author
- **Your Name**
- **Contact:** [Your Email]
- **GitHub:** [Your GitHub Profile URL]

## 📜 License
This project is licensed under the MIT License.

## 🤝 Contributions
Contributions are welcome! Feel free to open an issue or submit a pull request.

## ⭐ Acknowledgments
Thanks to the Google Apps Script community for their support and resources.

---
Happy scripting! 🚀