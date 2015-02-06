# pyWMATA
A python library for accessing the WMATA API for Washington DC Metro. 
##Usage
```python
  apikey = '' ###API keys available here https://developer.wmata.com/

  api = pyWMATA.WMATA(apikey)
```

=====
To get departure times for a given stationcode
```python
  stationcode = 'F01' #Gallery place metro

  times = api.getTrainDepartures(stationcode)
```
Returns a list of times until train departures from the given station.

=====
To get departure times for a given stationcode in a certain direction
```python
  stationcode = 'F01' #Gallery place metro
  
  times = api.getTrainDepartures(stationcode, 'Huntington', 'Franconia-Springfield')
  ```
Returns a list of times until train departures from the given station in the given direction.

=====
To get travel time needed to travel from one station to another
```python
  startStationCode = 'F01' #Gallery place metro
  endStationCode = 'A04' #Woodley Park metro
  
  totalTravelTime = getTravelTime(self, startStationCode, endStationCode)
```
Returns an integer that is the total time needed to go from one station to the next.

=====
To get a path from one station to another 
```python
  startStationCode = 'F01' #Gallery place metro
  
  endStationCode = 'A04' #Woodley Park metro
  
  stopsAlongPath = getPath(startStationCode, endStationCode)
````
Returns a list of station names along the path.

====
To get a station code for a given station
```python
  stationName = 'Woodley'
  
  stationCode = getStationcode(stationName)
````
Returns either a station code or None.

====
To get a station name for a given station code
```python
  stationCode = 'A04'
  
  stationName = getStationName(stationCode)
```
Returns either a station name or None. 

====
To get a station close to a location
```python
  lat = '38.8522750'
  lon = '-77.0423126'
  
  nearestStationCode = getNearestStation(lat, lon)
```
Returns the closest stationcode to the supplied location.

====
To check if their is an escalator or elevator problem at a station
```python
  stationCode = 'C13'
  
  elevatorsAndEscalatorsIncident = getElevatorEscalatorIncidentsAtStation(stationCode)
```
Returns True if there is an elevator or escalator outage and False if there is not.
