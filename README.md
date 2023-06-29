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
