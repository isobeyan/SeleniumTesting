# Selenium Web Application Testing — RentalAccessories

> **GitHub About description:**  
> *Automated end-to-end Selenium tests for a Django-based device rental web application — covering user registration, authentication, password management, and navigation flows with HTML reporting.*

Automated end-to-end test suite built with **Python** and **Selenium WebDriver** for the [RentalAccessories](https://github.com/mr-musfiqur/RentalAccessories) web application — a Django-based device rental platform.

The script exercises critical user-facing workflows (registration, login, password change/reset, navigation) and produces an HTML test report with screenshots for every step.

---

## Table of Contents

- [Features](#features)
- [Test Scenarios](#test-scenarios)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Sample Report](#sample-report)
- [Contributing](#contributing)
- [License](#license)

---

## Features

- **14 automated test cases** covering the full user journey
- **HTML report generation** with pass/fail/warning status per step
- **Automatic screenshots** captured at every assertion point
- **Assertion-based validation** on URLs and page titles
- **Exception handling** with descriptive warnings for unexpected failures

---

## Test Scenarios

| # | Test Case | Description | Validation |
|---|-----------|-------------|------------|
| 1 | Navigate to Register | Open the registration page | URL contains `/register/` |
| 2 | User Registration | Register a new user account | Page title matches expected value |
| 3 | View Profile | Access the user profile page | Page title assertion |
| 4 | Back to Home | Navigate back to the homepage | Page title assertion |
| 5 | Product Landing Page | Browse the product listing page | Page title assertion |
| 6 | Back to Home | Return to homepage from products | Page title assertion |
| 7 | Change Password | Update the account password | Successful form submission |
| 8 | Log Out | Log out of the application | URL contains `/logout/` |
| 9 | Home Page | Navigate to home as a guest | URL matches homepage |
| 10 | Password Reset Page | Open the password reset form | URL contains `/password-reset/` |
| 11 | Password Reset Submit | Submit a password reset request | URL contains `/password-reset/done/` |
| 12 | Navigate to Log In | Open the login page | URL contains `/login/` |
| 13 | Log In (new password) | Log in with the changed password | URL matches homepage |
| 14 | Exit (Log Out) | Final logout | URL contains `/logout/` |

---

## Tech Stack

| Tool / Library | Purpose |
|----------------|---------|
| [Python 3](https://www.python.org/) | Programming language |
| [Selenium WebDriver](https://www.selenium.dev/) | Browser automation |
| [Microsoft Edge WebDriver](https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/) | Browser driver |
| [pyhtmlreport](https://pypi.org/project/pyhtmlreport/) | HTML test report generation |

---

## Prerequisites

1. **Python 3.8+** installed ([download](https://www.python.org/downloads/))
2. **Microsoft Edge** browser installed
3. **Edge WebDriver** matching your Edge version ([download](https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/))
4. The **RentalAccessories** Django application running locally on `http://127.0.0.1:8000/`
   - Clone and set up: <https://github.com/mr-musfiqur/RentalAccessories>

---

## Installation

```bash
# 1. Clone this repository
git clone https://github.com/isobeyan/SeleniumTesting.git
cd SeleniumTesting

# 2. (Optional) Create and activate a virtual environment
python -m venv venv
source venv/bin/activate   # macOS / Linux
venv\Scripts\activate      # Windows

# 3. Install dependencies
pip install -r requirements.txt
```

---

## Usage

1. **Start the target application** — make sure the RentalAccessories Django server is running:

   ```bash
   # Inside the RentalAccessories project directory
   python manage.py runserver
   ```

2. **Update the WebDriver path** in `TestScript.py` (line 13–14) to point to your local Edge WebDriver executable:

   ```python
   driver = webdriver.Edge(
       executable_path="<path-to-your-msedgedriver>")
   ```

3. **Run the test script:**

   ```bash
   python TestScript.py
   ```

4. **View the report** — after execution an HTML report with screenshots is generated inside the `Reports/` directory. Open the `Report.html` file in any browser.

---

## Project Structure

```
SeleniumTesting/
├── TestScript.py           # Main test automation script (14 test cases)
├── requirements.txt        # Python dependencies
├── Reports/                # Generated HTML reports & screenshots
│   └── <timestamped run>/
│       ├── Report.html
│       └── Screenshots/
├── TestReportB1-G3.pdf     # Sample PDF test report
└── README.md               # Project documentation
```

---

## Sample Report

A sample test execution report is included in the repository:

- **HTML report:** `Reports/Device 10_26_2021 23_14_20/Report.html`
- **PDF report:** `TestReportB1-G3.pdf`

The HTML report provides a step-by-step breakdown with screenshots and pass/fail status for each test case.

---

## Contributing

Contributions, issues, and feature requests are welcome. Feel free to open an issue or submit a pull request.

---

## License

This project is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
