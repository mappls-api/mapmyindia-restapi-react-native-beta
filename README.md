![MapmyIndia APIs](https://www.mapmyindia.com/api/img/mapmyindia-api.png)

# Mapmyindia REST API SDK for React Native - beta

**Easy To Integrate Maps & Location APIs & SDKs For Web & Mobile Applications**

Powered with India's most comprehensive and robust mapping functionalities.
**Now Available**  for Srilanka, Nepal, Bhutan and Bangladesh

1. For full documentation contact MapmyIndia here:
Email: [apisupport@mapmyindia.com](mailto:apisupport@mapmyindia.com).
2. You can get your api key to be used in this document here: [https://www.mapmyindia.com/api/signup](https://www.mapmyindia.com/api/signup)
3. The beta code is provided to help you understand the basic functionality of MapmyIndia REST APIs working on React Native development platform. 

## Version History

| Version | Last Updated | Author |
| ---- | ---- | ---- |
| 0.0.3 | March 2019 | MapmyIndia API Team ([AS](https://github.com/anujsinghwd)) |


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


## Getting started

`$ npm install mapmyindia-restapi-react-native-beta --save`

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
  	project(':mapmyindia-restapi-react-native-beta').projectDir = new File(rootProject.projectDir, 	'../node_modules/mapmyindia-restapi-react-native-beta/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
      compile project(':mapmyindia-restapi-react-native-beta')
  	```

## Usage
```javascript
  import Mapmyindia from 'mapmyindia-restapi-react-native-beta';

```

### Methods

```javascript
  Mapmyindia.setRestApiKey('RestApiKey');
  Mapmyindia.setClientId('AtlasClietId');
  Mapmyindia.setClientSecret('AtlasClientSecret');
```
* <a href="#place-details">Place Details</a><br/>
* <a href="#route">Route</a><br/>
* <a href="#distance">Distance</a><br/>
* <a href="#atlas-autosuggest">Atlas AutoSuggest</a><br/>
* <a href="#atlas-nearby">Atlas NearBy</a><br/>
* <a href="#revgeocoding">RevGeocoding</a><br/>
* <a href="#atlas-geocoding">Atlas Geocoding</a><br/>
* <a href="#route-advance">Route Advance</a><br/>
* <a href="#route-eta">Route ETA</a><br/>
* <a href="#distance-matrix">Distance Matrix</a><br/>
* <a href="#distance-matrix-eta">Distance Matrix ETA</a><br/>

#### Place Details()

##### arguments
| Name | Required |
| ---- | :------: |
| `eloc` | `Yes` |
| `successCallback` | `Yes` |

```javascript
Mapmyindia.placeDetails({eloc: 'MMI000'}, (response) => {
        alert(JSON.stringify(response));
});
```

#### Route()

##### arguments
| Name | Required |
| ---- | :------: |
| `source` | `Yes` |
| `destination` | `Yes` |
| `alternatives` | `No` |
| `rtype` | `No` |
| `vtype` | `No` |
| `avoids` | `No` |
| `with_advices` | `No` |
| `with_traffics` | `No` |
| `viapoints` | `No` |
| `successCallback` | `Yes` |

```javascript
Mapmyindia.route({source: '28.111,77.111', destination: '28.22,77.22'}, (response) => {
        alert(JSON.stringify(response));
});
```

#### Distance()

##### arguments
| Name | Required |
| ---- | :------: |
| `center` | `Yes` |
| `pts` | `Yes` |
| `rtype` | `No` |
| `vtype` | `No` |
| `avoids` | `No` |
| `with_traffics` | `No` |
| `successCallback` | `Yes` |

```javascript
Mapmyindia.distance({center: '27.61234,77.61234', pts:'29,78|30,78|28,79'}, (response) => {
        alert(JSON.stringify(response));
});
```

#### Atlas AutoSuggest()

##### arguments
| Name | Required |
| ---- | :------: |
| `query` | `Yes` |
| `successCallback` | `Yes` |

```javascript
Mapmyindia.atlas_auto({query: 'agr'}, (response) => {
        alert(JSON.stringify(response));
});
```

#### Atlas NearBy()

##### arguments
| Name | Required |
| ---- | :------: |
| `keywords` | `Yes` |
| `refLocation` | `Yes` |
| `successCallback` | `Yes` |

```javascript
Mapmyindia.atlas_nearby({keywords: 'beer', refLocation: '28.631460,77.217423'}, (response) => {
        alert(JSON.stringify(response));
});
```

#### RevGeocoding()

##### arguments
| Name | Required |
| ---- | :------: |
| `lat` | `Yes` |
| `lng` | `Yes` |
| `successCallback` | `Yes` |

```javascript
Mapmyindia.rev_geocode({lat: '27.61234', lng: '77.61234'}, (response) => {
        alert(JSON.stringify(response));
});
```

#### Atlas Geocoding()

##### arguments
| Name | Required |
| ---- | :------: |
| `addr` | `Yes` |
| `itemCount` | `Yes` |
| `successCallback` | `Yes` |

```javascript
Mapmyindia.atlas_geocode({addr: 'lucknow',itemCount:'1'}, (response) => {
        alert(JSON.stringify(response));
});
```

#### Route Advance()

##### arguments
| Name | Required |
| ---- | :------: |
| `source` | `Yes` |
| `destination` | `Yes` |
| `alternatives` | `No` |
| `geometries` | `No` |
| `overview` | `No` |
| `steps` | `No` |
| `exclude` | `No` |
| `rtype` | `No` |
| `bearings` | `No` |
| `radiuses` | `No` |
| `region` | `No` |
| `advices` | `No` |
| `successCallback` | `Yes` |

```javascript
Mapmyindia.route_adv({`source`: '28.111,77.111', destination: '28.22,77.22'}, (response) => {
        alert(JSON.stringify(response));
});
```

#### Route ETA()

##### arguments
| Name | Required |
| ---- | :------: |
| `source` | `Yes` |
| `destination` | `Yes` |
| `alternatives` | `No` |
| `geometries` | `No` |
| `overview` | `No` |
| `steps` | `No` |
| `exclude` | `No` |
| `rtype` | `No` |
| `bearings` | `No` |
| `radiuses` | `No` |
| `region` | `No` |
| `advices` | `No` |
| `successCallback` | `Yes` |

```javascript
Mapmyindia.route_eta({`source`: '28.111,77.111', destination: '28.22,77.22'}, (response) => {
        alert(JSON.stringify(response));
});
```

#### Distance Matrix()

##### arguments
| Name | Required |
| ---- | :------: |
| `source` | `Yes` |
| `destinations` | `Yes` |
| `region` | `No` |
| `rtype` | `No` |
| `successCallback` | `Yes` |

```javascript
Mapmyindia.distance_matrix(source:'90.33687,23.470314',destinations:'90.379249,23.497178;90.497009,23.546286'}, (response) => {
        alert(JSON.stringify(response));
});
```


#### Distance Matrix ETA()

##### arguments
| Name | Required |
| ---- | :------: |
| `source` | `Yes` |
| `destinations` | `Yes` |
| `region` | `No` |
| `rtype` | `No` |
| `successCallback` | `Yes` |

```javascript
Mapmyindia.distance_matrix_eta(source:'90.33687,23.470314',destinations:'90.379249,23.497178;90.497009,23.546286'}, (response) => {
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


> © Copyright 2019. CE Info Systems Pvt. Ltd. All Rights Reserved. | [Terms & Conditions](http://www.mapmyindia.com/api/terms-&-conditions)
> mapbox-gl-native copyright (c) 2014-2019 Mapbox.
>  Written with [StackEdit](https://stackedit.io/) by MapmyIndia.