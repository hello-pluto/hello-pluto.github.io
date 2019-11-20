---
title: "AJAX, JSON and DataTables"
---

## AJAX, JSON and DataTables

The code snippet being used is:
```markdown
{
  "result": ［
    {
      "Name":"Amanda",
      "Username": "hello-pluto",
      "Favorites": ［
        {
          "Game": "PUBG",
          "Movie": "Harry Potter",
          "TVShow": "The Walking Dead",
          "Artiste": "Ed Sheeran"
        }
      ］,
      "Programmer": true,
      "SoftwareEngineer": true
    },
    {
      "Name": "Bob",
      "Username": "bobthebuilder",
      "Favorites": ［
        {
          "Game": "Vainglory",
          "Movie": "Wanderlust",
          "TVShow": "Game of Thrones",
          "Artiste": "Drake"
        }
      ］,
      "Programmer": true
      "SoftwareEngineer": false
    }
  ］
}
```

### To access JSON property directly

To access the specific property "Name" of the JSON object, I used the following code.

```markdown
table.row(this).data().Name
```
This was useful when I had to select a specific record and manipulate it's data.

### Access nested JSON data

This is necessary to access data that has an object returned in an array, as seen in the previous snippet.

The following piece of code shows that you need to access the element in the array, in this case **0** before accessing the Object's property.

```markdown
$('#example_table').DataTable({
  destroy: true,
  'ajax': {
    "type": "GET",
    "url": 'insert/link/here',
    "dataSrc": "result"
  },
    'columns': ［
      {"data": "Name"},
      {"data": "Username"},                
      {"data": "Favorites.0.Game"},
      {"data": "Favorites.0.Movie"},
      {"data": "Favorites.0.TVShow"},
      {"data": "Favorites.0.Artiste"},
      {"data": "Programmer"},
      {"data": "SoftwareEngineer"}
  ］
});
```
