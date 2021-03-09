# Calendar Screen

![Calendar](./images/calendar.JPG?raw=true)

- Download the [zip](https://github.com/tshailendra/Calendar-Screen/blob/main/CalendarEvents.zip) file
- From [PowerApps](https://make.powerapps.com/) > import canvas app option, select the downloaded zip file, to create the Calendar screen canvas app in your environment
- *ADD* **Office365Outlook Connector**
- Connect to Office365Outlook and select fields as required
```
ClearCollect(colEvents, ShowColumns(Office365Outlook.GetEventsCalendarViewV3("Calendar", 
    Text(startdate,DateTimeFormat.UTC), Text(enddate,DateTimeFormat.UTC)).value,"importance", "start", "end", "subject"))
```
- Map the subject to lblDateSchedule_1.Text

```
LookUp(colEvents, Text(DateValue(start),"[$-en-US]ddmmyyyy")= Text(ThisItem.currentdate,"[$-en-US]ddmmyyyy"),subject)
```

- Write your custom code in btnDate.OnSelect

# Screen Treeview

Order of the controls in the gallery:

![Treeview](./images/treeview.JPG?raw=true)
