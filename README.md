# Zmerge
Merge Zwift FIT file with QZ Fitness FIT file to add Zwift location data to QZ Fitness

Zmerge is used to resolve a problem - Zwift FIT files calculate elevation/altitude incorrectly for treadmill incline. Specifically, negative incline is assigned 0 elevation. QZ FIT files, when synced to Zwift activities, don’t contain Zwift's location data (virtual lat/long), but they do contain correct calculated elevation. Zmerge will merge Zwifts FIT location data (and any other important data fields) with QZs FIT data including calculated elevation.

Impacted routines:

- private void getZwiftData() {     
  - Read records from Zwift tables - record, session, lap_id - for selected fields for each record by timestamp - altitude, distance, latitude, longitude, speed

- private void createNewGarminFile() {
 - Ignore records that don't match a Zwift timestamp - only timestamp matching records are merged
 - Update the selected Garmin fields in tables - record, lap, session - altitude, distance, latitude, longitude, speed - revise to just update latitude and longitude in record table - done
 - Checks for manufacturer match to Garmin (file_id table) - skip - done
  
Outstanding issues:

- Should we merge the selected fields from Zwift tables?
  - Record (distance, speed)
  - Lap (distance, speed, time, virtual)
  - Session (speed, distance, time, virtual)
