# Review-Box-Capstone-Project
<img width="5712" height="4284" alt="Image" src="https://github.com/user-attachments/assets/475a4dda-d1c4-4535-8a38-7a2283facdef" />

The Review-Box is a mentometer (feedback device) specifically designed for school cafeterias. Built by Dag & Simba for their capstone project, this interactive system allows students to rate their daily meals and provides real-time feedback through an intuitive touchscreen interface. This repository contains detailed instructions and all necessary code for the project.

See this link for instructions on setting up your Google Sheet: https://docs.google.com/document/d/1egwhYvs6kNeSyEP7dpBwt4Gf0NozoCYfEVu8HTmKg3k/edit?usp=sharing

## Features

- **5-Point Rating System**: Students can vote using HATE, DISLIKE, NEUTRAL, LIKE, and LOVE buttons
- **Large Touchscreen Display**: 3.5" HX8357 TFT display for clear visibility in a busy cafeteria environment
- **Real-time Feedback**: Displays aggregated voting results as a bar chart
- **QR Code Integration**: Built-in QR code linking to Google Sheets for detailed vote tracking
- **WiFi Connectivity**: WPA2-Enterprise support for school network integration
- **Daily Food Updates**: Automatic daily updates of the menu item being rated
- **Batch Vote Processing**: Efficient vote aggregation before sending to cloud database
- **Swedish Language Support**: Display text in Swedish for Swedish school environment

## Installation

### Prerequisites
- Arduino IDE with ESP32 board support installed
- Required libraries (install via Arduino Library Manager):
  - Adafruit GFX Library
  - Adafruit HX8357 Driver
  - QRCodeGFX
  - U8g2 for Adafruit GFX
  - WiFi library (built-in for ESP32)
  - HTTPClient library (built-in for ESP32)
  - ArduinoJson

### Setup Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/DagBackerud/Review-Box-Capstone-Project-.git
   ```

2. **Install Dependencies**
   - Open Arduino IDE → Sketch → Include Library → Manage Libraries
   - Search for and install the libraries listed above

3. **Configure Credentials**
   - Copy `credentials.h.example` to `credentials.h`
   - Fill in your WiFi credentials:
     - `WIFI_SSID`: Your school network name
     - `WIFI_USERNAME`: Your WPA2-Enterprise username (if applicable)
     - `WIFI_PASSWORD`: Your WiFi password
     - `SERVER_NAME`: Your backend server endpoint for vote data

4. **Upload Code**
   - Connect your ESP32 board to your computer via USB
   - Open `main` file in Arduino IDE
   - Select the correct board (ESP32 Dev Module) and port
   - Click Upload

5. **Configure Google Sheet**
   - Follow the setup instructions: https://docs.google.com/document/d/1egwhYvs6kNeSyEP7dpBwt4Gf0NozoCYfEVu8HTmKg3k/edit?usp=sharing
   - Deploy the Google Apps Script code (included in the repository)

## Parts Used

### Electronics
- **Microcontroller**: ESP32 C5 DevkitC (32-bit dual-core processor with WiFi)
- **Display**: Adafruit HX8357 3.5" 480x320 TFT Touchscreen Display
- **Communication**: SPI interface for display
- **Power Supply**: USB power adapter

### Input Controls
- STEMMA Wired Push-Buttons
- **5 Buttons**: Connected to GPIO pins (25, 7, 26, 1, 0) for voting input
- **Button Labels**: HATE, DISLIKE, NEUTRAL, LIKE, LOVE

### Physical Components
- **3D Printed Case Parts** (Fusion 360 design files included):
  - Bottom body (`Bottom body.f3d`)
  - Support body (`Support body.f3d`)
  - Top cover (`Top cover.f3d`)

### Software Components
- **Display Libraries**: For rendering graphics and text on the TFT display
- **QR Code Generator**: For creating dynamic QR codes linking to vote tracking spreadsheet
- **WiFi & HTTP**: For connecting to school network and sending/receiving data
- **JSON Processing**: For parsing menu data and formatting vote submissions
- **Time Synchronization**: NTP-based system clock for accurate date/time stamping

### Backend Integration
- **Google Sheets**: Data storage and visualization of voting results
- **Google Apps Script**: Server-side processing of vote data
- **RESTful API**: Communication between ESP32 and backend services

---

**Project Team**: Dag & Simba  
**Class**: TE23TE  
**School**: [Swedish Gymnasium]
