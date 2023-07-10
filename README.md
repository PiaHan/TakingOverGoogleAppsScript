# TakingOverGoogleAppsScript

DB : BigQuery
Tool : Google Spread Sheet(Extensions -> Apps Script)

  <h6>DB</h6>
BigQuery, NoSQL DB. It helps create and manage DB easily but also hard to manage. 
Easy to insert the data but also hard to update or delete data because NoSQL has no key column so it allows duplication.
Take care about how to make program.
<List>Issue</List>
<ul>
  <li>If user insert the data from the google spread sheet, the sheet page clear</li>
  <li>If the sheet page is not cleared, it is editable page. And DB table is CREATE OR REPLACED everytime user update the data</li>
  <li>If the data has to be Unique, Check the data is exist in the DB before INSERT the data.(Using SELECT ~ WHERE ~)</li>
</ul>


<h5>Sheet</h5>
<h6>onEdit</h6>
<p>
  onEdit is the trigger that happens everytime user edit something(make event). If developer wants to access the DB using onEdit, developer should add the event at the Trigger Menu<b>(Apps Script -> Triggers(sidebar) -> Add Trigger)</b> 
</p>

<h6>Failure notification settings</h6>
Choose 'Notify Daily' or 'Notify Weekly'. Immediate error will be reported by users. Some errors happen but don't affect the workflow. 

<h6>Permission</h6>
<p>
  If the user is new to the program or have not enough permission, There might be permission Error.
  Ex. Access Denied.
  If this case happens, go to the <b>Google Colud -> IAM -> add the permission to user's account</b>
  I made a custom permission 'Warehouse', It is over-permissioned position but I will change it if I have time.
</p>

<h6>Connect Google Spread Sheet to Big Query</h6>
<p>
  <b>Apps Script -> Services -> press '+' button -> Add BigQuery, Google Spread Sheet</b>
</p>

<h5>All sheet users should know</h5>
<ul>
  <li>Don't make a blank row middle of the sheet list. Sunny trying to take care about it but in some pages, error could happen.</li>
  <li>Don't use the functions too fast. To make the sheet use automatically, to make the user comfortable to use, Most of the sheets use 'onEdit' Trigger. This is Trigger works everytime user make a difference in the sheet. <a href="https://developers.google.com/apps-script/guides/triggers?hl=ko">Trigger Reference link</a></li>
  
</ul>

<h5>Frequent issue happen</h5>
1. A stock's upc pop up when scan the B stock / No table error happen <br>
In this case, User might use sheets while updating DB. Sometimes updater forgot to run the 'initial Setting' Code. <br>
2. Date format error.<br>
User might change the date format, or add string data where only integer format allowed. Ask user that they edit the format or there is String data in the date / number / qty cell. <br>
3. Cell thinks 0 as null or blank.<br>
block the range cell -> Format -> number -> plain text. <br>
4. User input the number(integer, float) data but error message appears like 'String data can't be added to float or integer<br>
block the range cell -> Format -> number -> number <br>
These kinds of errors could happen to Date format DB too.<br>

<h5>How to make a button</h5>
<p>insert-> drawing -> start with text box.<br>
I used drawing button rather than image because image takes more time to load than drawing button.</p>
<h5>How to trigger event to the button</h5>
<p>Right click -> Assign Script</p>
<h5>Additional Explanation</h5>
<p>Video explanation of how to make DB table in Big Query console :<a href="https://drive.google.com/drive/folders/1XLi9X6WAIwyPKkfPtWJT3eKt89uPu-Ik?usp=sharing">Make DB Table(Location, Product)</a></p>
<p>Document about Append DB<a href = "https://drive.google.com/drive/folders/1AiqtQYFxnrMxdz46dMgmKTquZjIfyE1D?usp=drive_link">Apped DB with Doc</a></p>

<h5>Tip</h5>
<ul>
  <li>add .toUpper to SKU, UPC</li>
</ul>
