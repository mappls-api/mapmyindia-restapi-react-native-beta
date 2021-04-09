  

![MapmyIndia APIs](https://www.mapmyindia.com/api/img/mapmyindia-api.png)

  

# Mapmyindia REST API SDK for React Native - beta

  

**Easy To Integrate Maps & Location APIs & SDKs For Web & Mobile Applications**

  

Powered with India's most comprehensive and robust mapping functionalities.

**Now Available** for Srilanka, Nepal, Bhutan and Bangladesh

  

1. For full documentation contact MapmyIndia here:

Email: [apisupport@mapmyindia.com](mailto:apisupport@mapmyindia.com).

2. You can get your api key to be used in this document here: [https://www.mapmyindia.com/api/signup](https://www.mapmyindia.com/api/signup)

3. The beta code is provided to help you understand the basic functionality of MapmyIndia REST APIs working on React Native development platform.

  

## Version History

  

| Version | Last Updated | Author |
| ---- | ---- | ---- |
| 0.0.11 | April 2021 | MapmyIndia API Team ([MS](https://github.com/mamtasharma117)) |
| 0.0.11 | February 2021 | MapmyIndia API Team ([MA](https://github.com/mdakram)) |
| 0.0.10 | January 2021 | MapmyIndia API Team ([MA](https://github.com/mdakram)) |
| 0.0.9 | October 2020 | MapmyIndia API Team ([MA](https://github.com/mdakram)) |
| 0.0.8 | March 2019 | MapmyIndia API Team ([BM](https://github.com/balmukandpathak)) |

  
  

## What is Mapmyindia?

  

Mapmyindia is the location data platform for mobile and web applications. We provide [building blocks](https://www.mapmyindia.com/) to add location features like maps, search, and navigation into any experience you create. Use our simple and powerful APIs & SDKs for interactivity and control.

  

## Sign up for Mapmyindia

  

Not a Mapmyindia user yet? [Sign up for an account here](https://www.mapmyindia.com/api/signup). Once you’re signed in, all you need to start building is a Mapmyindia key. Use this same short code with all of our interactive mapping libraries, JavaScript SDKs, and directly against our REST APIs. You can create and manage your access tokens on your [Mapmyindia Account page](https://www.mapmyindia.com/api/dashboard).

  

## API Usage

Your MapmyIndia Maps SDK usage needs a set of license keys ([get them here](http://www.mapmyindia.com/api/signup) ) and is governed by the API [terms and conditions](https://www.mapmyindia.com/api/terms-&-conditions).

As part of the terms and conditions, you cannot remove or hide the MapmyIndia logo and copyright information in your project.

Please see [branding guidelines](https://www.mapmyindia.com/api/advanced-maps/API-Branding-Guidelines.pdf) on MapmyIndia [website](https://www.mapmyindia.com/api) for more details.

The allowed SDK hits are described on the plans page. Note that your usage is

shared between platforms, so the API hits you make from a web application, Android app or an iOS app all add up to your allowed daily limit.

  
  

# mapmyindia-restapi-react-native-beta

  

## Getting started

  

`$ npm install mapmyindia-restapi-react-native-beta --save`

  

If you are using React-Native < `0.60.0` then you have to follow additional steps which are below

### Mostly automatic installation

  

`$ react-native link mapmyindia-restapi-react-native-beta`

  

### Manual installation

  
  

#### iOS

  

1. In XCode, in the project navigator, right click `Libraries` ➜ `Add Files to [your project's name]`

2. Go to `node_modules` ➜ `mapmyindia-restapi-react-native-beta` and add `RNRestapi.xcodeproj`

3. In XCode, in the project navigator, select your project. Add `libRNRestapi.a` to your project's `Build Phases` ➜ `Link Binary With Libraries`

4. Run your project (`Cmd+R`)<

  

#### Android

  

1. Open up `android/app/src/main/java/[...]/MainActivity.java`

- Add `import com.restapi.reactnative.RNRestapiPackage;` to the imports at the top of the file

- Add `new RNRestapiPackage()` to the list returned by the `getPackages()` method

2. Append the following lines to `android/settings.gradle`:

```

include ':mapmyindia-restapi-react-native-beta'

project(':mapmyindia-restapi-react-native-beta').projectDir = new File(rootProject.projectDir, '../node_modules/mapmyindia-restapi-react-native-beta/android')

```

3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:

```

compile project(':mapmyindia-restapi-react-native-beta')

```

  

## Usage

```javascript

import  Mapmyindia  from  'mapmyindia-restapi-react-native-beta';
```

  

### Methods

  

```javascript

Mapmyindia.setRestApiKey('RestApiKey');

Mapmyindia.setClientId('AtlasClietId');

Mapmyindia.setClientSecret('AtlasClientSecret');

```

*  <a  href="#place-details">Place Details</a><br/>

*  <a  href="#atlas-autosuggest">Atlas AutoSuggest</a><br/>

*  <a  href="#atlas-nearby">Atlas NearBy</a><br/>

*  <a  href="#revgeocoding">RevGeocoding</a><br/>

*  <a  href="#atlas-geocoding">Atlas Geocoding</a><br/>

*  <a  href="#route-advance">Route Advance</a><br/>

*  <a  href="#route-eta">Route ETA</a><br/>

*  <a  href="#distance-matrix">Distance Matrix</a><br/>

*  <a  href="#distance-matrix-eta">Distance Matrix ETA</a><br/>

  
### Place Details()

The Place detail API is to extract the details of a place with the help of its eLoc i.e. a 6 character code. Since a place may or may not have additional attributes associated with it, the response from the place details may be different for each record. However the response will be an extract from an existing set of master key-value pairs grouped as objects.
  

#### Request Parameters
##### a. Mandatory Parameters:

1.  **eloc**: the id or eLoc of the place whose details are required. The 6-digit alphanumeric  
    code for any location. (e.g. mmi000).
2. **response** : successcallback of api call
  

```javascript

Mapmyindia.place_details({eloc: 'MMI000'}, (response) => {

alert(JSON.stringify(response));

});

```
## [Place Detail with Sub Template based Configuration](#Place_Detail_with_Sub_Template_based_Configuration)

The API is highly configurable to  configuration enables to provide the required set of attributes to the user on the basis of assigned sub templates.
The default configuration with available with basic pay-as-you-go rates is that of `General Details` subtemplate.

## [Response Parameters for Place Details - Sub Templates](#Response_Parameters_for_Place_Details-Sub_Templates)

The parameters are group in sub templates. Here is the list of attributes with sub template information.  

#### [Subtemplate 1 : General Details](#Subtemplate_1_:_Sbt_general_details)
1.	Eloc (string) : 6 characters alphanumeric unique identifier 
2.	placeName (string) : Name of the place 
3.	address (string) : address of the place 
4.	type: defines the type of location matched (HOUSE_NUMBER, HOUSE_NAME, POI, 
	STREET, SUB_LOCALITY, LOCALITY, VILLAGE, DISTRICT, SUB_DISTRICT, CITY, STATE, 
     SUBSUBLOCALITY, PINCODE)

#### [Subtemplate 2 : Admin Tokens (PREMIUM OFFERING)](#Subtemplate_2_:_sbt_admin_token)
1.	city (string): The name of the city in which the location exists.
2.	district (string): The name of the district in which the location exists.
3.	pincode (string): The pin code of the location area.
4.	subDistrict (string): The name of the sub-district in which the location exists. 
5.	state (string): The name of the state in which the location exists.

#### [Subtemplate 3 : Address Tokens (PREMIUM OFFERING)](#Subtemplate_3_:_sbt_address_token)
1.	houseNumber (string): The house number of the location. 
2.	houseName (string): The name of the location.
3.	locality (string): The name of the locality where the location exists. 
4.	street (string): The name of the street of the location.
5.	subSubLocality (string): The name of the sub-sub-locality where the location exists. 
6.	subLocality (string): The name of the sub-locality where the location exists.
7.	village (string): The name of the village if the location exists in a village.
8.	poi (string): The name of the POI if the location is a place of interest (POI).

#### [Subtemplate 4 : Contact Details (PREMIUM OFFERING)](#Subtemplate_4_:_sbt_contact_details)

1.	Email
2.	Mobile
3.	Telephone
4.	Website


#### [Subtemplate 5 : Location Coordinates (PREMIUM OFFERING)](#Subtemplate_5_:_sbt_loc_coordinates)

1.	latitude(double): The latitude of the location. 
2.	longitude(double): The longitude of the location.

#### [Subtemplate 6 : E/E Coordinates (PREMIUM OFFERING)](#Subtemplate_6_:_sbt_nav_coordinates)

1.	Entry_lat(double):The entry latitude of the location.
2.	Entry_lon(double):The entry longitude of the location.
  

### Atlas AutoSuggest()

  

####  Request Parameters
##### a. Mandatory Parameters:
1. **query**  (string) e.g. Shoes, Coffee, Versace, Gucci, H&M, Adidas, Starbucks, B130 {POI, House Number, keyword, tag}
2. **response** : successcallback of api call


##### b. Optional Parameters:

1.  **location**  {string (latitude[double],longitude[double])} e.g. location=28.454,77.435
2.  **zoom**  (double) = takes the zoom level of the current scope of the map (min: 4, max: 18).
4.  **tokenizeAddress**  (boolean) = provides the different address attributes in a structured object.
5.  **pod**  (string) = it takes in the place type code which helps in restricting the results to certain chosen type.  
    Below mentioned are the codes for the pod -  
    1.  **SLC**: Sublocality
    2.  **LC**: Locality
    3.  **CITY**: City
    4.  **VLG**: Village
    5.  **SDIST**: Subdistrict
    6.  **DIST**: District
    7.  **STATE**: State
    8.  **SSLC**: Subsublocality
6.  **filter**  = this parameter helps you restrict the result either by mentioning a bounded area or to certain eloc (6 digit code to any poi, locality, city, etc.), below mentioned are the both types -  
    a.  **filter**  = bounds: lat1, lng1; lat2, lng2 (latitude, longitude) {e.g. filter=bounds: 28.598882, 77.212407; 28.467375, 77.353513}  
    b.  **filter**  = cop: {eloc} (string) {e.g. filter=cop:YMCZ0J}

  

```javascript

Mapmyindia.atlas_auto({query: 'agr'}, (response) => {

alert(JSON.stringify(response));

});

```

  

### Atlas NearBy()
####  Request Parameters
##### a. Mandatory Parameters:
  
1.  **keywords** (string) e.g. FODCOF, Shoes, Coffee, Versace, Gucci, H&M, Adidas, Starbucks, B130 {POI, House Number, keyword, tag}
2.  **refLocation**  {string (latitude[double],longitude[double])}: Provides the location around which the search will be performed. It also supports Eloc. E.g. refLocation=28.454,77.435 or refLocation="MMI000"
4. **response** : successcallback of api call

##### b. Optional Parameters:
1.  **page**  (integer): provides number of the page to provide results from.
2.  **sort**  (string): provides configured sorting operations for the client on cloud. Below are the available sorts:  
    a)  **dist:asc**  &  **dist:desc**  - will sort data in order of distance from the passed location (default).  
    b)  **name:asc**  &  **name:desc**  - will sort the data on alphabetically bases.
3.  **radius**  (integer): provides the range of distance to search over (default: 1000, min: 500, max: 10000).
4.  **bounds** (string) : Allows the developer to send in map bounds to provide a nearby search within the bounds.
    {e.g. (bounds("28.56812,77.240519;28.532790,77.290854"))
5.   **filter** (string) : This parameter helps you get a specific type of EV charging Station
    -   **filter** = model:(string);brandId:(string);plugType:(string)
  

```javascript

Mapmyindia.atlas_nearby({keywords: 'beer', refLocation: '28.631460,77.217423'}, (response) => {

alert(JSON.stringify(response));

});

```

  

### RevGeocoding()

####  Request Parameters
##### a. Mandatory Parameters:
1.  **lat**:(double) the latitude of the location for which the address is required.
2.  **lng**:(double) the longitude of the location for which address is required.
3. **response** : successcallback of api call


```javascript

Mapmyindia.rev_geocode({lat: '27.61234', lng: '77.61234'}, (response) => {

alert(JSON.stringify(response));

});

```

  

### Atlas Geocoding()

####  Request Parameters
##### a. Mandatory Parameters:

1.  **address**(string) address to be geocoded e.g. 237 Okhla industrial estate phase 3 new delhi, delhi 110020
2. **response** : successcallback of api call

##### b. Optional Parameters:
  1.  **itemCount**  (integer): parameter can be set to get maximum number of result items from the API (default: 1).
2.  **bias**  (integer): This parameter can be used to set Urban or Rural bias. A positive value sets the Urban bias and a negative value sets Rural bias. Allowed values are:
    -   0 : Default: (No bias)
    -   -1 : Rural
    -   1 : Urban
3.  **podFilter**  (string): This parameter can be used to set admin level restriction. The result will be either the given admin level or equivalent admin or higher in the hierarchy. No lower admin will be considered for geocoding. Allowed values are:
    -   **hno**  : house number
    -   **hna**  : house name
    -   **poi**  : point of interest
    -   **street**  : street
    -   **sslc**  : sub sub locality
    -   **village**  : village
    -   **slc**  : sub locality
    -   **sdist**  : sub district
    -   **loc**  : locality
    -   **city**  : city
    -   **dist**  : district
    -   **pincode**  :pincode
    -   **state**  : state
4.  **bound**  (string): This parameter can be used to set admin boundary, which means geocoding will be done within the given admin. The allowed admin bounds are Sub-District, District, City, State and Pincode. The parameter accepts the admin eLoc as value.


**Note**: Please note that podFilter & bound parameters are mutually exclusive. They cannot be used together in an API call.

```javascript

Mapmyindia.atlas_geocode({address: 'lucknow',itemCount:'1'}, (response) => {

alert(JSON.stringify(response));

});

```

  

### Route Advance()

  

####  Request Parameters
##### a. Mandatory Parameters:
1. **source**:{string (longitude[double],latitude[double])}
2. **destination**: is pair of comma separated longitude & latitude value.Last coordinate will be considered as end point (mandatory) and those in between are via points (optional). Example: {longitude},{latitude};{longitude},{latitude}
3. **response** : successcallback of api call
##### b. Optional Parameters:
1.  **geometries(string)**: This parameter used to change the route geometry format/density (influences overview and per step). Default value is
    -   polyline with 5 digit precision;
    -   polyline6 for 6 digit precision;
    -   geojson for geometries as geojson.
2.  **steps(boolean)**: Return route steps for each route leg. Possible values are true/false. By default it will be used as false. <Recommended=false; unless otherwise recommended by MapmyIndia>
3.  **exclude(string)**: Additive list of road classes to avoid, order does not matter. Possible values are toll, motorway & ferry. Multiple values can be sent separated by.
4.  **rtype**: type of route (integer) required for navigation, where values mean:
    -   0 optimal (default)
    -   1 shortest (it will calculate route by excluding access penalties like private roads, etc.)
5.  **region(string)**: This parameter is optional for India; for other countries (Sri Lanka, Nepal, Bangladesh & Bhutan) this parameter is mandatory. Possible values are ind (for India, default), lka (for Sri Lanka) , npl (for Nepal) , bgd (for Bangladesh) and btn (for Bhutan)
6.  **bearings(integer)**: Limits the search to segments with given bearing in degrees. The referencing will be to the true north and in clockwise direction. (shall be part of premium offering)
7.  **alternatives**  Search for alternative routes. Passing a number: e.g. alternatives=n searches for up to n alternative routes. Please note that even if alternative routes are requested, a result cannot be guaranteed.
8.  **radiuses** Limits the search to given radius in meters. For all way-points including start and end points. {radius};{radius}[;{radius} ...]. (shall be part of premium offering).
9.  **overview(string)**: Add overview geometry either full, simplified according to highest zoom level it could be display on, or not at all. Possible values could be simplified (default), full, false. (shall be part of premium offering)
10. **profile** :(string ) default driving

```javascript

Mapmyindia.route_adv({`source`: '28.111,77.111', destination: '28.22,77.22'}, (response) => {

alert(JSON.stringify(response));

});

```

  

#### Route ETA()

  

####  Request Parameters
##### a. Mandatory Parameters:
1. **source**:{string (longitude[double],latitude[double])}
2. **destination**: is pair of comma separated longitude & latitude value.Last coordinate will be considered as end point (mandatory) and those in between are via points (optional). Example: {longitude},{latitude};{longitude},{latitude}
3. **response** : successcallback of api call
##### b. Optional Parameters:
1.  **geometries(string)**: This parameter used to change the route geometry format/density (influences overview and per step). Default value is
    -   polyline with 5 digit precision;
    -   polyline6 for 6 digit precision;
    -   geojson for geometries as geojson.
2.  **steps(boolean)**: Return route steps for each route leg. Possible values are true/false. By default it will be used as false. <Recommended=false; unless otherwise recommended by MapmyIndia>
3.  **exclude(string)**: Additive list of road classes to avoid, order does not matter. Possible values are toll, motorway & ferry. Multiple values can be sent separated by.
4.  **rtype ** type of route (integer) required for navigation, where values mean:
    -   0 optimal (default)
    -   1 shortest (it will calculate route by excluding access penalties like private roads, etc.)
5.  **region(string)**: This parameter is optional for India; for other countries (Sri Lanka, Nepal, Bangladesh & Bhutan) this parameter is mandatory. Possible values are ind (for India, default), lka (for Sri Lanka) , npl (for Nepal) , bgd (for Bangladesh) and btn (for Bhutan)
6.  **bearings(integer)**: Limits the search to segments with given bearing in degrees. The referencing will be to the true north and in clockwise direction. (shall be part of premium offering)
7.  **alternatives**  Search for alternative routes. Passing a number: e.g. alternatives=n searches for up to n alternative routes. Please note that even if alternative routes are requested, a result cannot be guaranteed.
8.  **radiuses** Limits the search to given radius in meters. For all way-points including start and end points. {radius};{radius}[;{radius} ...]. (shall be part of premium offering).
9.  **overview(string)**: Add overview geometry either full, simplified according to highest zoom level it could be display on, or not at all. Possible values could be simplified (default), full, false. (shall be part of premium offering)
10. **profile** :(string ) default driving
```javascript

Mapmyindia.route_eta({`source`: '28.111,77.111', destination: '28.22,77.22'}, (response) => {

alert(JSON.stringify(response));

});

```

  

#### Distance Matrix()


##### a. Mandatory Parameters:
1. **source**:{string (longitude[double],latitude[double])}
2. **destinations**: is pair of comma separated longitude & latitude value.Last coordinate will be considered as end point (mandatory) and those in between are via points (optional). Example: {longitude},{latitude};{longitude},{latitude}
3. **response** : successcallback of api call
##### b. Optional Parameters:
1.  **rtype**  type of route (integer) required for navigation, where values mean:
    -   **0**  optimal (default)
    -   **1**  shortest (it will calculate route by excluding access penalties like private roads, etc.)
2.  **region**(string): This parameter is optional for India; for other countries (Sri Lanka, Nepal, Bangladesh & Bhutan) this parameter is mandatory. Possible values are  **ind**  (for India, default),  **lka**  (for Sri Lanka) ,  **npl**  (for Nepal) ,  **bgd**  (for Bangladesh) and  **btn**  (for Bhutan)
3. **profile** :(string ) default driving


```javascript

Mapmyindia.distance_matrix(source:'90.33687,23.470314',destinations:'90.379249,23.497178;90.497009,23.546286'}, (response) => {

alert(JSON.stringify(response));

});

```

  
  

#### Distance Matrix ETA()

  ##### a. Mandatory Parameters:
1. **source**:{string (longitude[double],latitude[double])}
2. **destinations**: is pair of comma separated longitude & latitude value.Last coordinate will be considered as end point (mandatory) and those in between are via points (optional). Example: {longitude},{latitude};{longitude},{latitude}
3. **response** : successcallback of api call
##### b. Optional Parameters:
1.  **rtype**  type of route (integer) required for navigation, where values mean:
    -   **0**  optimal (default)
    -   **1**  shortest (it will calculate route by excluding access penalties like private roads, etc.)
2.  **region**(string): This parameter is optional for India; for other countries (Sri Lanka, Nepal, Bangladesh & Bhutan) this parameter is mandatory. Possible values are  **ind**  (for India, default),  **lka**  (for Sri Lanka) ,  **npl**  (for Nepal) ,  **bgd**  (for Bangladesh) and  **btn**  (for Bhutan)
3. **profile** :(string ) default driving


```javascript

Mapmyindia.distance_matrix_eta(source:'90.33687,23.470314',destinations:'90.379249,23.497178;90.497009,23.546286'}, (response) => {

alert(JSON.stringify(response));

});

```
### Legacy Place Details API - Place Details()

  

#### Request Parameters
##### a. Mandatory Parameters:

1.  **eloc**: the id or eLoc of the place whose details are required. The 6-digit alphanumeric  
    code for any location. (e.g. mmi000).
2. **response** : successcallback of api call
  

```javascript

Mapmyindia.placeDetails({eloc: 'MMI000'}, (response) => {

alert(JSON.stringify(response));

});

```
  
  

For any queries and support, please contact:

  

![Email](https://www.google.com/a/cpanel/mapmyindia.co.in/images/logo.gif?service=google_gsuite)

Email us at [apisupport@mapmyindia.com](mailto:apisupport@mapmyindia.com)

  

![](https://www.mapmyindia.com/api/img/icons/stack-overflow.png)

[Stack Overflow](https://stackoverflow.com/questions/tagged/mapmyindia-api)

Ask a question under the mapmyindia-api

  

![](https://www.mapmyindia.com/api/img/icons/support.png)

[Support](https://www.mapmyindia.com/api/index.php#f_cont)

Need support? contact us!

  

![](https://www.mapmyindia.com/api/img/icons/blog.png)

[Blog](http://www.mapmyindia.com/blog/)

Read about the latest updates & customer stories

  
  

> © Copyright 2021. CE Info Systems Pvt. Ltd. All Rights Reserved. | [Terms & Conditions](http://www.mapmyindia.com/api/terms-&-conditions)
