# Translink Passenger Information Displays

As is commonplace for app development, I felt bored one day and decided taking on this project. It took ages figuring out how GTFS-RT worked. And how Translink dealt with it. And how different it is between modes of transport. Whatever, regardless, I now have a "finished" product!

## Requirements
Windows 10 64-bit and newer is officially supported, as well as Windows Server 2012 and newer. These requirements come from that of Microsoft's .NET Desktop Runtime 8.0.  

While you may have success launching on Windows 7, it's half broken so take that as you will.  

Haven't tested on Arm64 so let me know how well it works. Should be fairly problem free if Windows translation is good enough? Oh, you're absolutely not getting this working on Windows RT or 15035, I've tried, good luck 😅

## How to use
Open the executable, easy as that. To set your own stop IDs, double click the text that says "Service". To change the board's title, double click the title. You'll find quite a few things you can double click in this software.

## Download
From the [Releases page](https://github.com/jaydenridley4/Translink-Passenger-Information-Displays/releases/tag/latest) of the GitHub repository.  
Source is available on the [GitHub repository](https://github.com/jaydenridley4/Translink-Passenger-Information-Displays) itself.

## Screenshots
![Departure board for Central station](/translink-pids/1.png "Departure board for Central station")
![Ferny Grove train stop list](/translink-pids/2.png "Ferny Grove train stop list")
![Departure board for Ipswich station](/translink-pids/3.png "Departure board for Ipswich station")
![Brisbane Airtrain service stop list](/translink-pids/4.png "Brisbane Airtrain service stop list")

## Keyboard Combinations
Different keyboard combinations control different aspects of the software as you may expect. Below is a list of shortcuts you may use:

### Train board

|Combination		 |Description													|
|----------------|------------------------------------------------------------------|
|`Alt+Q`				 |Toggle between departure list and stop list				|
|`Alt+R`				 |Refresh													|
|`Alt+N`				 |Toggle visibility of the NGR marker						|
|`Alt+F`				 |Enter a broken full screen mode (960x540 resolution, lol)	|

