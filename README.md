# Google Sheets with Python

# This is the project for performing operations on Google Sheets with Python.

## Installing APIs :-
Go to https://console.developers.google.com and start a new project.

Then enable Drive API and Sheets API for the project.

## Creating credentials to use the API :-
In https://console.developers.google.com go to credentials option in left menu.

Create a new service key.

Select service account -> New service account (if no service account exists).

Enter Service account name and role (permission given to this account for the drive operations).

Download the credentials json file.

Transfer the json file in project folder. 

## Python Code :-
### Libraries needed :-
gspread and oauth2client.

oauth2client authorises the user to access files based on the permission given in credentials json file.

gspread allows operations on Google Sheets.

Set the scope of access to Sheets and Drive by defining scope as ['https://spreadsheets.google.com/feeds','https://www.googleapis.com/auth/drive']

Fetch credentials from json file through ServiceAccountCredentials in oauth2client.

Authorize through gspread.

### Operations that can be performed on Sheets :-
create() -> creates a new spreadsheet which will contain all the worksheets.

share(email,scope) -> share the sheet with email in credentials json file to give access as per the permission granted and scope defined.

open() -> opens a spreadsheet for editing a worksheet in it.

worksheets() -> returns a list of all the worksheets in the spreadsheet.

add_worksheet(title=name, rows=row, cols=col) -> adds a worksheet with the given title and number of rows and columns.

del_worksheet(worksheet) -> deletes a worksheet.

get_worksheet(i) -> gets ith worksheet (i>=0).

worksheet.get_all_records() -> gets all the rows and columns values in the worksheet as a dictionary.

append_row([a,b]) -> adds a and b to a row.

worksheet.row_values(i) -> gets ith row value from worksheet.

worksheet.update_acell(cell, value) -> updates the cell(eg ->'A3') with the value.

worksheet.acell(cell).value -> gets value from the cell(eg ->'A3').

There are many more operations which can be referred from the link below.

## Links referred :-
https://github.com/burnash/gspread

https://www.youtube.com/watch?v=7I2s81TsCnc

https://cloud.google.com/iam/docs/granting-roles-to-service-accounts

https://gspread.readthedocs.io/en/latest/
