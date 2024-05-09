Cleaning:
1. Checks
    1. There are no duplicates
    2. Strings of spaces are used as NaN values - removed
    3. 0 is used to encode NaN for some values of location, latitude, longitude
2. Filtering
    1. Droppping rows if latitude and longitude aren't defined and ON and CROSS street names are not defined
3. Imputation
    1. Use On and Cross street to impute location if unique
    2. Use Neonatim to find location if On and Cross location is not unqiue. Successful pulls are saved in location_data.json as {place, location.raw} where place = row['ON STREET NAME'] + " " + str(row(BOROUGH))/"new york"
    3. Use location(lat, long) to impute lat and long where they are nan/0
    4. Imputing ZIP CODE
        1. Where zipcode does not exist, use location if location does not disagree on zipcode
        2. Else, if row already in zip_dict, use that
        3. Else, check location_dict to impute 
        4. Else, look up with nominatim and if it exists, add to zip_dict
    5. Impute number of persons injured/killed by adding pedestrians+cyclists+motorist injured/killed
3. Sanity checks
    1. Check if zipcode matches borough
        1. Fix borough if necessary
