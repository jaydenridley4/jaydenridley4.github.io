# Translink Passenger Information Displays

As is commonplace for app development, I felt bored one day and decided taking on this project. It took ages figuring out how GTFS-RT worked. And how Translink dealt with it. And how different it is between modes of transport. Whatever, regardless, I now have a "finished" product!

## Requirements
Windows 10 64-bit and newer is officially supported, as well as Windows Server 2012 and newer. These requirements come from that of Microsoft's .NET Desktop Runtime 8.0.
While you may have success launching on Windows 7, it's half broken so take that as you will.
Haven't tested on Arm64 so let me know how well it works. Should be fairly problem free if Windows translation is good enough? Oh, you're absolutely not getting this working on Windows RT or 15035, I've tried, good luck 😅

## Screenshots
TBA

## Keyboard Combinations
Different keyboard combinations control different aspects of the software as you may expect. Below is a list of shortcuts you may use:

### Train board

|Combination		 |Description													|
|----------------|------------------------------------------------------------------|
|`Alt+Q`				 |Toggle between departure list and stop list				|
|`Alt+R`				 |Refresh													|
|`Alt+N`				 |Toggle visibility of the NGR marker						|
|`Alt+F`				 |Enter a broken full screen mode (960x540 resolution, lol)	|