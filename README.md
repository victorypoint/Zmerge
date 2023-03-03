# Zmerge
Merge Zwift FIT file with QZ Fitness FIT file to add Zwift location data to QZ Fitness

Zmerge is used to resolve a problem - Zwift FIT files calculate elevation/altitude incorrectly for treadmill incline. Specifically, negative incline is assigned 0 elevation. QZ FIT files, when synced to Zwift activities, don’t contain Zwift's location data (virtual lat/long), but they do contain correct calculated elevation. Zmerge will merge Zwift FIT location data (and other important data fields) with QZ FIT data including calculated elevation.

Zmerge is a Java app with GUI. 
- Requires Garmin FIT SDK.
- Requires Oracle Java™ Runtime Environment 8 - 1.8.0 or higher.
- To compile: javac zmerge/*.java
- To run: java zmerge/Zmerge
