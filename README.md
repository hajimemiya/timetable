# timetable

import requests

# Get the timetable from the Transport for London website
url = "https://api.tfl.gov.uk/journey/journeys/find/from/Mornington%20Crescent/to/any/departure/now"
response = requests.get(url)

# Parse the timetable JSON response
timetable = response.json()

# Extract the list of departures
departures = timetable["departures"]

# Print the timetable
for departure in departures:
  print(departure["time"], departure["destination"])
