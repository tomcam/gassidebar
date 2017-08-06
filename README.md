# Google Apps Script spread sidebar example

## TODO:
* Document approval process required to run Apps Script code
* How to put up a msgbox to display a value
* How to obtain a value from a form submit
* Illustrate with Firefox screenshots
* Add a style sheet

This example creates a sidebar app in Google Apps Script to obtain all the mails from a particular person during a specified month.

Create a spreadsheet:

* From inside Google Docs, choose `File` > `New` > `Spreadsheet`.

* Save it under a name such as `mailsheet`.

Start writing the script for this spreadsheet:

* From the `Tools` menu, choose `Script editor...`

A window opens up with a new file named Code.gs and a stub function:

````
function myFunction() {
  
}
````

* Save your project immediately.

* Either press `Ctrl+S` (`Command+S` on Apple systems) or select the `File` menu and choose `Save`.

A dialog appears asking you to edit the project name.

* Type in a name, say, `mailreport`, and click `OK`.

* Select all the text by pressing `Ctrl+A` or `Command+A` (on Apple systems) and press backspace to delete it.

* Replace it with this code:

````
function onOpen() {
  setupSidebar()
}

function setupSidebar() {
  var html = HtmlService.createHtmlOutputFromFile('GetMonth')
      .setTitle('Generate tax report')
      .setWidth(300);
  SpreadsheetApp.getUi() // Or DocumentApp or FormApp.
      .showSidebar(html);
}
````

## Save your progress

* Save your work so far. Either press `Ctrl+S` (`Command+S` on Apple systems) or select the `File` menu and choose `Save`.

## Create a dialog that obtains a month and year from the user

The sidebar is a form that you'll save as an HTML file. Here's a start:

* From the `File` menu, choose `New` > `Html file` and gave it the name `GetMonth`. No extension is needed: an  `.html` extension is added automatically.

Here is the stub code:

````
<!DOCTYPE html>
<html>
  <head>
    <base target="_top">
  </head>
  <body>
    
  </body>
</html>
````

*  Replace it with this: 

````
<div>
    <div>
		<label for="text-date">Date</label>
    </div>
    <input type="text" name="date" id="text-date" >
    <input type="button" value="Close" onclick="google.script.host.close()" />
</div>
````

* Save your progress again.

