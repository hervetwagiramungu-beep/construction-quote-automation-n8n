# Construction Quote Automation (n8n)

An n8n workflow that handles quote requests for a construction company, from the moment a client fills in a form to the moment the owner gets an alert.

## What it does

1. A client submits a quote request through an online form (name, email, phone, project type, location, budget, description).
2. Google Gemini reads the description and assigns a **category** (New House, Renovation, Road/Infrastructure, Commercial Building, Other) and an **urgency** level (Low, Medium, High).
3. The request is saved as a new row in a Google Sheet, including the category and urgency.
4. The client receives an automatic confirmation email.
5. The company owner receives an alert email with all the details.

## Workflow

Form trigger → Gemini (classify) → Edit Fields → Google Sheets → Client email (Gmail) → Owner email (Gmail)

## Tools used

- n8n
- Google Gemini
- Google Sheets
- Gmail

## How to use this workflow

1. In n8n, import `Construction Quote Requests.json`.
2. Create a Google Sheet with these headers in row 1: Date, Name, Email, Phone, Project type, Location, Budget, Description, Category, Urgency.
3. Replace `YOUR_SHEET_ID` in the Google Sheets node by selecting your own sheet.
4. Replace `owner@example.com` in the owner email node with the real owner address.
5. Connect your own Google Sheets, Gmail and Gemini credentials.

## Author

Built by Twagiramungu Herve, a civil engineer learning AI automation.
