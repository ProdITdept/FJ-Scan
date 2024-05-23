# Finger Joint Card Scanning Attendance System
The Finger Joint Card Scanning Attendance System is designed to automate attendance tracking using RFID cards and Arduino-based scanning devices. This README will guide you through setting up the hardware and software components necessary for this system.

## Arduino Code for Card Scanning
# Hardware Setup
**Components:**
- Arduino Uno or compatible board
- RFID reader module (e.g., MFRC522)
- RFID cards or tags

**Wiring:**
- Connect the RFID reader module to the Arduino according to the manufacturer's specifications.
- Ensure proper power and ground connections.
- Connect the data pins (e.g., SDA, SCK, MOSI, MISO) from the RFID module to the corresponding pins on the Arduino.

## Code Explanation
**1. Libraries:**
- Include the necessary libraries for interfacing with the RFID reader module and communicating with the Arduino.

**2. Define Pins:**
- Define the pins used for communication with the RFID module.

**3. Initialize RFID Module:**
- Initialize the RFID reader module and prepare it for reading cards.

**4. Main Loop:**
- Continuously check for RFID cards within the vicinity.
- When a card is detected, read its unique identifier and store it for further processing.
- Optionally, perform additional actions based on the scanned card (e.g., logging attendance, triggering events).

**5. Functions:**
- Define any helper functions needed for the main operation of the system.

## ERPNext Doctype Setup
**Prerequisites**
- Ensure you have ERPNext installed and running.
- You need administrator access to ERPNext to create and configure doctypes.

## Step-by-Step Setup
**Create the Attendance Log Doctype**

**1. Log in to ERPNext:**
- Open your ERPNext instance and log in with your administrator credentials.

**2. Navigate to Doctype List:**
- Go to the ERPNext Desk.
- In the search bar, type "DocType List" and select it.

**3. Create a New Doctype:**
- Click the "New" button to create a new doctype.
- Fill in the following details:
- - **Name:** Attendance Log
- - **Module:** Choose the relevant module (e.g., HR or Custom).
- - **Naming:** By "naming_series" field
- Save the doctype.


**Add Fields to the Doctype**
**Fields:**
- Timestamp, Employee ID, Employee Name, Department, RFID Card ID, Status
- Ensure to mark Employee ID, Employee Name, RFID Card ID as mandatory fields.

**Configure Naming Series**
**1. Open Naming Series:**
- In the search bar, type "Naming Series" and select it.
- Add a new naming series for the Attendance Log doctype with the format YY.MM.DD.###.

**2. Assign Naming Series to Doctype:**
- Go back to the Attendance Log doctype.
- Set the "Naming Series" field to the format you created (YY.MM.DD.###).

**Finalize and Test**
**1. Save and Publish:**
- Save the Attendance Log doctype.
- Ensure there are no validation errors and the doctype is published.

**2. Test the Doctype:**
- Create a new Attendance Log document to test the setup.
- Verify that all fields are present and correctly configured.
- Ensure the naming series is applied correctly.

**Additional Configurations (Optional)**
**Permissions:**
- Configure permissions to control who can create, read, update, and delete Attendance Log documents.

**Custom Scripts:**
- Add custom scripts if you need additional automation or validations.

## Node-RED Flow
**1. Import the Flow:**
- Import the provided Node-RED flow file (e.g., FingerJointCardScanningAttendance.json) into your Node-RED instance.

**2. Configure Nodes:**
- Configure the nodes in the flow to interact with your Arduino device and ERPNext instance.
- Ensure proper communication between the hardware (Arduino) and software (Node-RED).

**3. Test the Flow:**
- Test the flow by simulating card scans and verifying that attendance logs are correctly recorded in ERPNext.

## Conclusion
By following these steps, you have successfully set up the Finger Joint Card Scanning Attendance System. The hardware components (Arduino-based card scanner) and software components (ERPNext doctype setup and Node-RED flow) work together to automate attendance tracking efficiently. Ensure to test thoroughly and adjust configurations as necessary to fit your specific requirements.


Author: *Joel*




