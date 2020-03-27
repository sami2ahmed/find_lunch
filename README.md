# find_lunch
Using Foursquare’s API to find lunch. The specific data I used was collected from Foursquare’s API. My program finds the top Foursquare restaurants given some location data. I will not be covering API authentication etc. because you can do that by following Foursquare’s thorough documentation.
Input: user provides their current location in the form of latitude and longitude, path to JSON file, and desired max radius in miles that they are willing to travel to grab their lunch. Max radius will have an upper limit of 25 miles, and lower limit of 0 miles.
Output: list of restaurants.
The steps that the program goes through are:
Extract JSON file. The data we’re using in this example is downloaded from Foursquare’s API for a location in downtown Chicago.
Filter out irrelevant JSON elements. Like most JSON, the data returned from Foursquare’s API was pretty verbose. I filter down to necessary data only.
Transform JSON to a datatype that is easier to iterate over. I took the filtered JSON created a list of dictionaries to inevitably get my data into a neat Pandas’s dataframe.
Filter the dataframe to only restaurants. The Foursquare API returns more than just restaurants.
Calculate distance, and add assert errors to handle max radius that is too large (>25mi.) or small (<0mi.). This step references a helper function that takes in lat/long of restaurant and calculates distance from the starting point in miles.
