### A Python application for NY Bravest FCU Database Management

NY Bravest provides firefighters with loans and benefits and data must be relayed between other financial companies. This app simplifies the communications between several financial institutions, saving time while increasing accuracy. It was designed as an executable for Windows. The application must be stored in the same directory as the associated database file, NYBravestDB.xlsx.
cycle.

#### Week One

Open the app. The user should have saved an Employee Election spreadsheet with adds and changes for the current week's payroll. Click the top-left button and a pop-up will ask the user to navigate to the directory with this file. The file is automatically identified as the most recent with the format "EmployeeElection_yyyymmdd.xls". It must be opened throught the app to have the correct format. The user can add records in addition to those already in the spreadsheet. Enter new records at the bottom of the first sheet but do not alter the columns. Save your changes.

The second button down on the left makes a new text file from these records. It's named "PNET...txt" and is saved in the current week's directory, ready to be forwarded to the Office of Payroll Administration (OPA.)

#### Week Two

At this point, OPA has recieved a file and replied with the file named "PEDT...txt" indicating the amount of payroll they'll be sending. The bottom-left button does a few things. First, it updates the database file with last week's records. Second, it adds a column to store this week's OPA amounts and compares these amounts to the records in the database. Does a member have a different payroll deduction amount in the database? Does the new file include unrecognized members? Were accounts rejected? Payroll totals and discrepancies are listed in a new Excel file with the format "yyyymmdd_analysis.xls," which opens automatically when the process completes.

If no further changes are necessary, create the FC.txt file to forward on to FedComp with the top-right button. If changes are made and a new *winston-all* sheet is needed, use the middle button on the right. The NYBravestDB.xlsx file can be viewed and edited directly using the bottom-right button.

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

**1.3.0** Small isual improvements. Analysis button now shows totals and discrepant records in Excel rather than the in the GUI and pop-out window. Fixed error that happened when database had stray cells filled.

**1.4.0** Winston_all sheet now sorts by first, last, and MI. EE sheet added "W" option for withhold from OPA but add to Winston sheet.

**1.4.1** Getting 'No engine found for xls' in a new environment. Added the parameter to df.to_excel.