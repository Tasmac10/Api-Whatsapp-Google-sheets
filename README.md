# WhatsApp Message Automation with Google Sheets

Send automated WhatsApp messages by fetching phone numbers from a Google Sheet using Python and Selenium.

## Features:
- Import recipient phone numbers directly from a Google Sheet.
- Automated login and message sending through WhatsApp Web.
- Handle different phone number formats.

## Prerequisites:

1. **Python Libraries**: 
    - `selenium`: For automating the web browser interaction.
    - `pandas`: For handling and processing data.
    - `requests`: For making HTTP requests.
    - `webdriver_manager`: For managing the web driver.

2. **Web Driver**:
    - ChromeDriver: Necessary to interface with the Chrome browser.

3. **Setup & Configuration**:
    - A Google Sheet with a column titled 'Number' for the phone numbers.
    - The Google Sheet should be publicly accessible for reading or appropriate credentials should be set.

## Setup:

1. **Python Environment Setup**:
    ```bash
    # Create a virtual environment (optional but recommended)
    python3 -m venv env
    source env/bin/activate  # On Windows, use: env\Scripts\activate

    # Install the required packages
    pip install selenium pandas requests webdriver_manager
    ```

2. **ChromeDriver Setup**:
    - Install ChromeDriver using `webdriver_manager` which simplifies the process:
        ```python
        from webdriver_manager.chrome import ChromeDriverManager
        ChromeDriverManager().install()
        ```
    - Or you can manually download the [ChromeDriver](https://sites.google.com/a/chromium.org/chromedriver/) which matches your Chrome browser version.
    - Place the `chromedriver.exe` (or appropriate executable for your system) in a directory listed in your system's PATH.

## Usage:

1. Set the `message` variable in the script with your desired message.
2. Replace `'sheets id'` in the `sheets_id` variable with the actual ID of your Google Sheet.
3. Run the script. When it opens `https://web.whatsapp.com/`, scan the QR code using your WhatsApp mobile app.
4. The script will then fetch phone numbers from the Google Sheet and start sending messages.

## Notes:
- It's essential to ensure that the Google Sheet containing the phone numbers is accessible publicly or has been shared with the correct credentials.
- Respect the terms of service of WhatsApp. Using such automation scripts might violate their terms, leading to account restrictions.
- Ensure the phone numbers in the Google Sheet are in a valid international format.
- The script will skip any numbers that lead to errors and continue with the next one.
