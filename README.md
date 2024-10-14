# **Billing-System**
Billing System with Python and MySql

## Libraries Incl.
Here’s a list of libraries used in the Bill Management System code:

1. **Tkinter**: 
   - Used for creating the graphical user interface (GUI) of the application.

2. **random**: 
   - Utilized to generate random bill numbers.

3. **Pillow (PIL)**: 
   - Used for image processing, specifically for handling QR code images.

4. **qrcode**: 
   - A library to generate QR codes that contain billing information.

5. **openpyxl**: 
   - Used for reading from and writing to Excel files to save bill records.

6. **os**: 
   - Used for interacting with the operating system, such as checking file existence and managing directories.

7. **pathlib**: 
   - Used for handling file paths in a more intuitive way.

8. **MySQL Connector (if implemented)**: 
   - If you're using MySQL for storing bill data, this library would be required to establish a connection between Python and the MySQL database.

9. **messagebox**: 
   - Part of Tkinter, used for displaying dialog boxes for user notifications and errors.

These libraries together enable the functionality and features of the Bill Management System, from user interface design to data storage and management.

To change the MySQL parameters in your Bill Management System, follow these instructions:

## Instructions for Changing MySQL Parameters

1. **Install MySQL Connector** (if not already installed):
   Ensure you have the MySQL Connector library installed in your Python environment. You can install it using pip:
   ```bash
   pip install mysql-connector-python
   ```

2. **Locate Database Connection Code**:
   In your code, find the section where you establish the connection to the MySQL database. It typically looks like this:

   ```python
   import mysql.connector

   conn = mysql.connector.connect(
       host='your_host',      # Change this to your database host
       user='your_username',  # Change this to your database username
       password='your_password', # Change this to your database password
       database='your_database'  # Change this to your database name
   )
   cursor = conn.cursor()
   ```

3. **Change the Parameters**:
   Update the parameters in the `connect` function with your MySQL credentials:
   - **host**: Change `'your_host'` to the hostname or IP address of your MySQL server. For local servers, you can use `'localhost'` or `'127.0.0.1'`.
   - **user**: Change `'your_username'` to your MySQL username.
   - **password**: Change `'your_password'` to your MySQL password.
   - **database**: Change `'your_database'` to the name of the database you want to connect to.

   Example:
   ```python
   conn = mysql.connector.connect(
       host='localhost',
       user='root',
       password='my_secure_password',
       database='bill_management'
   )
   ```

4. **Ensure Database Table Exists**:
   Make sure that the table you intend to use for storing bills exists in your MySQL database. You can create it using the following SQL query:

   ```sql
   CREATE TABLE bill (
       bill_number INT PRIMARY KEY,
       dosa INT,
       coffee INT,
       tea INT,
       biryani INT,
       chapati INT,
       puri INT,
       total_price DECIMAL(10, 2)
   );
   ```

5. **Test the Connection**:
   After making changes, run your application to ensure that it successfully connects to the MySQL database and that you can perform operations like inserting and retrieving data.

By following these steps, you can successfully update the MySQL connection parameters in your Bill Management System.

## Installation Code

You can create a Python script to install all the required libraries using the `pip` package manager. Below is a code snippet that you can run in your terminal or save as a `.py` file and execute.

```python
import subprocess
import sys

# List of libraries to install
libraries = [
    'mysql-connector-python',  # MySQL connector
    'pillow',                  # Pillow for image processing
    'qrcode',                  # QR code generation
    'openpyxl'                # Excel file handling
]

# Function to install libraries
def install(package):
    subprocess.check_call([sys.executable, '-m', 'pip', 'install', package])

# Install all libraries
for library in libraries:
    try:
        install(library)
        print(f'Successfully installed {library}')
    except Exception as e:
        print(f'Failed to install {library}: {e}')
```

### Instructions to Run the Code

1. **Open a Text Editor**: Open your favorite text editor or IDE (like VSCode, PyCharm, or even Notepad).

2. **Copy the Code**: Copy the above code snippet into the editor.

3. **Save the File**: Save the file with a name like `install_libraries.py`.

4. **Open Terminal/Command Prompt**:
   - Navigate to the directory where you saved the `install_libraries.py` file.

5. **Run the Script**:
   Execute the script using Python:
   ```bash
   python install_libraries.py
   ```

This script will attempt to install each library in the list using `pip`. Make sure you have internet access for the installations to succeed. If you're using a virtual environment, ensure it's activated before running the script.
