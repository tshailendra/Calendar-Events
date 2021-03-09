# Calendar Screen

![Calendar](./images/calendar.JPG?raw=true)


- Connect to Office365Outlook and select fields as required
```
ClearCollect(colEvents, ShowColumns(Office365Outlook.GetEventsCalendarViewV3("Calendar", Text(startdate,DateTimeFormat.UTC), Text(enddate,DateTimeFormat.UTC)).value,"importance", "start", "end", "subject"))
```
- Map the subject to lblDateSchedule_1

```
LookUp(colEvents, Text(DateValue(start),"[$-en-US]ddmmyyyy")= Text(ThisItem.currentdate,"[$-en-US]ddmmyyyy"),subject)
```

# Screen Treeview

Order of the controls in the gallery:

![Treeview](./images/treeview.JPG?raw=true)
