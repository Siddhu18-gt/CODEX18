# Medixa - Smart Healthcare Management System

A comprehensive, secure, and paperless hospital management system designed to interconnect all hospital modules efficiently.

## Project Overview

Medixa aligns perfectly with the hackathon vision at Presidency University, as it integrates AI-powered healthcare solutions to solve real-world medical challenges, making it a strong and impactful project for such competitions.

## Features

🌐 System Modules & Features
Landing Page:
Single-page application with Home, Portals, About Us, and Contact Us sections
Receptionists Portal:
Patient management, doctor management, and billing
Doctor Portal:
Patient login, doctor page, patient reports, and test reports
Others Portal:
Test department and nurse modules
Patient Portal:
View reports and billing information
🤖 AI & Smart Features
AI Report Analyzer:
Extracts key medical values from reports
Detects abnormal parameters
Generates smart summaries
AI Chatbot Integration:
Helps users navigate the system
Answers basic health-related queries

## Technology Stack

- **Frontend**: HTML5, CSS3, JavaScript (Vanilla)
- **Backend**: PHP (XAMPP)
- **Database**: MySQL
- **Font**: Inter (Bold, Semi-Bold, Regular)
- **Icons**: Font Awesome 6.4.0
- **prediction**: python,ML.
- **dataset**: CSV file(for disease pridiction)


## Installation & Setup

### Prerequisites

1. XAMPP Server installed
2. Web browser (Chrome, Firefox, Edge)
3. Text editor (VS Code recommended)

### Setup Steps

1. **Clone/Download the project**
   ```bash
   # Place the MEDIXA folder in xampp/htdocs/
   # Path should be: C:\xampp\htdocs\MEDIXA
   ```

2. **Start XAMPP Services**
   - Open XAMPP Control Panel
   - Start Apache
   - Start MySQL

3. **Create Database**
   - Open phpMyAdmin (http://localhost/phpmyadmin)
   - Import the SQL file: `database/schema.sql`
   - This will create the `medixa_db` database with all required tables and demo data

4. **Configure Database Connection**
   - Edit `config/database.php` if needed (default settings should work)
   - Default settings:
     - Host: localhost
     - User: root
     - Password: (empty)
     - Database: medixa_db

5. **Access the Application**
   - Open browser and navigate to: `http://localhost/MEDIXA/`
   - The landing page should load

## Default Login Credentials

### Receptionist
- **Email**: (Register a new account)
- **Password**: (Set during registration)

### Doctors (Pre-populated)
- **Email**: rajesh.kumar@medixa.com
- **Password**: password
- (Same for all pre-populated doctors)

### Test Departments
- **Email**: blood@medixa.com
- **Password**: password
- (Same for all test departments)

### Nurses
- **Email**: nurse.sarah@medixa.com
- **Password**: password

### Demo Aadhaar Numbers
- `1234 5678 9012` - Rajesh Kumar
- `2345 6789 0123` - Priya Sharma
- `3456 7890 1234` - Amit Patel
- `4567 8901 2345` - Sneha Reddy
- `5678 9012 3456` - Vikram Singh

## Project Structure

```
MEDIXA/
├── api/                    
├── assets/
│   ├── css/
│   ├── js/
│   └── images/
├── config/
│   └── database.php       
├── database/
│   └── schema.sql         
├── dataset/
│   └── training_dataset.csv  # CSV used for AI predictions
├── portals/
│   ├── restricted/        
│   ├── doctor/           
│   ├── others/         
│   ├── patient/         
│   └── predict.html        # Prediction module
├── index.html            
└── README.md

## Key Features Implementation

### Aadhaar Integration
- Demo Aadhaar numbers are pre-populated in the database
- When a valid demo Aadhaar is entered and "Fetch Details" is clicked, patient details are auto-filled
- Format: XXXX XXXX XXXX (auto-formatted)

### Patient Registration Flow
1. Enter Aadhaar number
2. Click "Fetch Details" → Auto-fills patient information
3. Enter cause, select specialization, select doctor
4. Click "Register" → Saves to patients table

### Patient Login Flow
1. Enter Aadhaar number
2. Click "Login" → Shows patient details
3. Options: Final Report, Doctor Page

### Billing System
1. Enter patient Aadhaar and load patient
2. Add tests with amounts
3. Set status (Paid/Unpaid)
4. Click "Save" → Calculates subtotal, discount, total
5. Select scheme (BPL 50%, General 0%, Insurance 30%)
6. Download bill

###AI Prediction Module
   File: portals/predict.html
   Uses training_dataset.csv to predict patient-related outcomes
   Workflow:
   Upload training CSV
   Train model (Python backend)
   Predict outcomes for new patient data

### Interconnections
- When billing status is set to "Paid", patient details automatically appear in test departments
- When doctor clicks "Summarize", patient report is generated and visible in patient portal
- When nurse checks medicine checkbox, doctor sees "Given" status

## Development Notes

- All passwords are hashed using PHP's `password_hash()` function
- Sessions are used for authentication
- Aadhaar numbers are formatted automatically (XXXX XXXX XXXX)
- All forms have validation
- Responsive design for mobile and desktop
- Professional UI with small font sizes (13px base)
- Icons from Font Awesome for better UX

## Troubleshooting

### Database Connection Error
- Check if MySQL is running in XAMPP
- Verify database credentials in `config/database.php`
- Ensure database `medixa_db` exists

### Aadhaar Fetch Not Working
- Verify demo Aadhaar numbers in `demo_aadhaar_data` table
- Check API endpoint: `api/fetch_aadhaar.php`
- Ensure Aadhaar format is correct (12 digits)

### Session Issues
- Clear browser cache and cookies
- Check PHP session configuration
- Ensure `session_start()` is called in API files

## Future Enhancements

- Real Aadhaar API integration (when available)
- Email notifications
- SMS alerts
- Advanced reporting
- Mobile app
- Multi-language support

## Team

- **Akash** - Software Developer
- **Vaibhav** - Software Developer
- **Siddu** - Software Developer
- **Vijay** - Software Developer

## License

This project is developed for Hackthon in Precidency University

## Support

For issues or questions, please refer to the project documentation or contact the development team.

---

**Note**: This is a demo system. For production use, implement proper security measures, real Aadhaar API integration, and comply with healthcare data regulations.

