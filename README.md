# route
google app script to do geocoding from location/town names in Australia to gpx. Just copy into the sheet app editor.

Need to create a google sheets with headings and locations for:
1) Route Name
2) GPX Route

With columns for:

1) location/town
2) state
3) name
4) lat
5) lon
6) point

ie
|||
|---|---|
|Route Name|QLD Trip|
|GPX Route|*generated*|

|location|state|name|lat|lon|point|
|--------|-----|----|---|---|-----|
|Longreach|QLD|*generated*|*generated*|*generated*|*generated*|

Need to update constants at the top of the script to locate each of these. This sheet is referred to as the work sheet below.

you will need to get an api key from https://geocode.maps.co and add it to the callGeo function.
you will need to set routeType to select the type of gpx route you want. My nav software for example appears not to support RTE routes.

Referring to the "Work" Sheet:

1) create a list of locations/towns in column A
2) list the state the town in column 2.
3) Under the "GPX" menu press "Geocode". This will populate the name, lat and lon columns. 
4) You can fill any empty/failed to find by hand. The name is optional, if left blank it will use the first column
5) Under the "GPX" menu press "Points". This will populate the points column ie the individual waypoint xml
6) If you want the route to be named, fill in the route name in the second column at the top. this is also required to save a file
7) Under the "GPX" menu press "Route" and the GPX route cell will be populated.
8) check you have a name set and press the save button. This will create a gpx file in the same folder on drive
9) import into your navigation software.

Other menu commands:

Clear Points will remove all generated points
Clear Route will clear just the GPX route cell
Clear Generated will remove all the geocoded values, points and route.
Clear All will clear everything except the headings

GPS Coordinates Precision and type

You need to use decimal or aka WGS84 format GPS coordinates eg -17.795529	145.3121906
the less decimal points the more likely you will have trouble finding the specific spot. If it is a town then probably not an issue. A geocache then try for six or over.
