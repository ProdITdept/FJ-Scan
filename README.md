# Finger Joint Card Scanning Attendance System
The Finger Joint Card Scanning Attendance System is designed to automate attendance tracking using RFID cards and Arduino-based scanning devices. This README will guide you through setting up the hardware and software components necessary for this system.

## Arduino Code for Card Scanning
# Hardware Setup
**Components**
- ESP8266 microcontroller (e.g., NodeMCU)
- HW-898-A v0.1 card scanner module
- RFID cards or tags

**Wiring**
Connect the HW-898-A v0.1 card scanner module to the ESP8266 as follows:

- HW-898-A v0.1 --> ESP8266
- VCC --> 3.3V
- GND --> GND
- TX --> RX (GPIO pin specified in code)
- RX --> TX (GPIO pin specified in code)

*Ensure proper power and ground connections between the components.*


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
- - **Name:** *Corner Sample*
- - **Module:** Choose any relevant module (e.g., HR or Custom).
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
![image](https://github.com/ProdITdept/FJ-Scan/assets/168414219/4d201433-70d0-460d-b29f-d6e4a20d38d3)


**2. Configure Nodes:**
- Configure the nodes in the flow to interact with your Arduino device and ERPNext instance.
- Ensure proper communication between the hardware (Arduino) and software (Node-RED).
![image](https://github.com/ProdITdept/FJ-Scan/assets/168414219/24f48a8a-00fd-46ce-b8fc-52cac7113b25)

**3. Test the Flow:**
- Test the flow by simulating card scans and verifying that attendance logs are correctly recorded in ERPNext.

## Conclusion
By following these steps, you have successfully set up the Finger Joint Card Scanning Attendance System. The hardware components (Arduino-based card scanner) and software components (ERPNext doctype setup and Node-RED flow) work together to automate attendance tracking efficiently. Ensure to test thoroughly and adjust configurations as necessary to fit your specific requirements.


Author: *Joel*




