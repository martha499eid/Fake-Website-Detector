# Fake Website Detector

Fake Website Detector is a web-based security project designed to help users identify potentially malicious and phishing websites by analyzing URLs and evaluating different security risk indicators.

The system aims to make website safety checks easier by providing users with a risk assessment, a risk score, and information about detected security indicators.

## Project Objectives

- Help users identify potentially fake, malicious, or phishing websites.
- Analyze submitted URLs using external website security APIs.
- Evaluate different risk indicators to estimate website security risks.
- Calculate an overall risk score and classify the result into a risk level.
- Store website information and scan results for future reference.
- Provide users with clear and understandable scan results.

## How It Works

1. The user enters a website URL.
2. The backend receives and validates the submitted URL.
3. The system checks the URL using external security services.
4. The returned information is analyzed against predefined risk indicators.
5. A risk score is calculated based on the detected indicators and their assigned weights.
6. The website is classified into a risk level.
7. The scan results are stored in the Oracle database.
8. The user receives a report explaining the detected risks.

> Note: The system provides risk assessments based on available security data. It cannot guarantee that a website is completely safe.

## Technologies Used

### Frontend
- HTML5
- CSS3
- Bootstrap
- JavaScript

### Backend
- PHP

### Database
- Oracle Database
- Oracle SQL

### Security Services
- VirusTotal API
- Google Safe Browsing API

## Database Structure

The project uses four main tables to organize website information, security indicators, and scan results.

| Table | Description |
|---|---|
| WEBSITES | Stores website URLs, domains, and registration dates. |
| RISK_INDICATORS | Stores security risk indicators, descriptions, and weights. |
| SCAN_RESULTS | Stores scan dates, risk levels, and calculated risk scores. |
| SCAN_INDICATORS | Connects scan results with detected risk indicators. |

### Database Relationships

- One website can have multiple scan results.
- One scan result can contain multiple risk indicators.
- One risk indicator can appear in multiple scan results.
- SCAN_INDICATORS acts as a junction table to manage the many-to-many relationship between scans and risk indicators.

## Project Architecture

The application consists of three main layers:

1. Frontend Layer: Provides the user interface for submitting URLs and viewing scan reports.
2. Backend Layer: Handles URL validation, API communication, risk analysis, score calculation, and database operations.
3. Database Layer: Stores websites, risk indicators, and scan history using Oracle Database.

## Security Considerations

- Validate submitted URLs before processing them.
- Use secure methods when communicating with external APIs.
- Keep API keys and database credentials private.
- Avoid exposing sensitive configuration files in the public repository.
- Do not treat an unchecked or unknown website as safe.

## Project Status

Currently in Development

The Oracle database structure has been created, and PHP-to-Oracle connectivity has been successfully tested.

Frontend development, API integration, automated risk analysis, and result reporting are planned implementation stages.

## Project Structure

`text
Fake-Website-Detector/
│
├── database/
│   └── schema.sql
│
├── frontend/
│
├── backend/
│
├── README.md
└── .gitignore
