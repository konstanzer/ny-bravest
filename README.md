### A Python application for NY Bravest FCU Database Management

NY Bravest provides firefighters with loans and benefits and data must be relayed between other financial companies. This app simplifies the communications between several financial institutions, saving time while increasing accuracy. It was designed as an executable for Windows. Its size is 44 MB. The application must be stored in the same directory as the associated database file, NYBravestDB.xlsx.

### How to use it

Open the program. This will create two windows. The console window is for debugging and can be minimized. The main window has a Norman Rockwell painting from the November, 1953 edition of the Saturday Evening Post. To the left of the image are six ordered buttons corresponding to the credit union's payroll cycle.

#### Week One

The user will have saved a spreadsheet with adds and changes in a directory for the current week's payroll. Click the top button and a pop-up will ask the user to navigate to the directory with this file. The Excel file is automatically identified as the most recent with the format "EmployeeElection_yyyymmdd.xls". Selecting the directory will launch Excel where the user can add records in addition to those already in the spreadsheet. Enter new records at the bottom of the first sheet but do not alter the columns. Save your changes.

The second button down makes a new text file from these records. It's named "PNET...txt" and is saved in the current week's directory, ready to be forwarded to the Office of Payroll Administration (OPA.)

#### Week Two

At this point, OPA has recieved a file and replied with the file named "PEDT...txt" indicating the amount of payroll they'll be sending. The middle button does a few things. First, it updates the database file with new and changed records. Second, it adds a column to store this week's OPA amounts and compares these amounts to the records in the database. Does a member have a different payroll deduction amount in the database? Does the new file include unrecognized members? Were some accounts rejected? All of these discrepancies are listed in a pop-up window. Finally, it updates the *winston-all* sheet in the NY_Bravest_DB.csv file.

At this point, if no further changes are necessary, generate the FC.txt file to forward on to FedComp with the fourth button. If changes are made and a new *winston-all* sheet is needed, use the fifth button, which generates the sheet without using the "PEDT...txt" file again. The NYBravestDB.xlsx file can be edited directly using the bottom button.

### Troubleshooting

The console window that opens with the main GUI may point you in the right direction. Here are some possible mistakes.

* editing a filename
* editing a column name
* double entries
* leaving the database open while trying to update it

### Changelog

**1.2.0** adds the *Generate new Winston sheet* button and *Winston total this week* to the main interface. The *Amount to FedComp* total is deleted on account of redundancy. The *winston-all* sheet is now included in the database file, which is now an Excel workbook and not a csv file. This version adds a *note* column to the *EmployeeElection* sheet. A console window now opens with the application for help with debugging. It also fixes a bug when naming the "PNET...txt" file and another when making newline characters in the FC.txt file.
**1.2.1** Fixed value error raised for mixed integers and datetimes. Now it just skips invalid dates.
**1.2.2** Fixed date column merge error (object and datetime) when adding new records.
**1.2.3** Fixed note column merge error that happened when Employee Election sheet had no notes.