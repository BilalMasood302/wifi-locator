This version implements:

Useful even with one AP if differences in signal strength are noticeable(might work better with some tweaking)

MainActivity:
> used for displaying map and your location on the map(bitmap image)
> Designed for fixed layout for 800x600 display in Landscape position
MapNetwork:
> Saving Scan values to corresponding coordinates (mapping the floor)
Search:
> Spinner for displaying, per-programmed locations
SQLocate:
> SQLite database, that handles mapping and reading location
> Based on NewBoston android video tutorial(if you'll need any reference)
WiFiDemo & WiFiScanReceiver:
> Scans only the currently available networks
> mostly referenced from http://stackoverflow.com/questions/13920185/scanning-available-wifi-detect-specific-strongest-wifi-ssid-to-launch-an-xml-ac

Wiki is currently just copy-paste from project report wiki and is in Slovenian. When time will allow I will translate it and mend the layout.