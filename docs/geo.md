# Protocol Documentation
<a name="top"></a>

---
Module: `module`
Package: `opencannabis.module`
Domain: rfc.opencannabis.info
---


## Reference Documentation

- [opencannabis/geo/Address.proto](#opencannabis/geo/Address.proto)
  - [Address](#opencannabis.geo.Address)

- [opencannabis/geo/Country.proto](#opencannabis/geo/Country.proto)
  - [Country](#opencannabis.geo.Country)

- [opencannabis/geo/Distance.proto](#opencannabis/geo/Distance.proto)
  - [Distance](#opencannabis.geo.Distance)
  - [DistanceValue](#opencannabis.geo.DistanceValue)
  - [LocationAccuracy](#opencannabis.geo.LocationAccuracy)

  - [DistanceUnit](#opencannabis.geo.DistanceUnit)

- [opencannabis/geo/Geohash.proto](#opencannabis/geo/Geohash.proto)
  - [Geohash](#opencannabis.geo.Geohash)

- [opencannabis/geo/Point.proto](#opencannabis/geo/Point.proto)
  - [MapCoordinate](#opencannabis.geo.MapCoordinate)
  - [MapPosition](#opencannabis.geo.MapPosition)
  - [Point](#opencannabis.geo.Point)
  - [WorldCoordinate](#opencannabis.geo.WorldCoordinate)

- [opencannabis/geo/Location.proto](#opencannabis/geo/Location.proto)
  - [Location](#opencannabis.geo.Location)

- [opencannabis/geo/USState.proto](#opencannabis/geo/USState.proto)
  - [USState](#opencannabis.geo.usa.USState)

- [opencannabis/geo/Province.proto](#opencannabis/geo/Province.proto)
  - [Province](#opencannabis.geo.Province)





<a name="opencannabis/geo/Address.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## opencannabis/geo/Address.proto
Provides a structure to specify a standard postal address.


<a name="opencannabis.geo.Address"></a>

### Address
Specifies a standard postal address, with two address lines, and space for a municipality ('city'), provincial
authority ('state'), and national authority ('country').


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| first_line | [string](#string) |  | First line of the address. |
| second_line | [string](#string) |  | Second line of the address, if applicable. |
| city | [string](#string) |  | City or municipality name for the address. |
| state | [string](#string) |  | State that contains the city or municipality for this address. |
| zipcode | [string](#string) |  | USPS zipcode associated with this address. |
| country | [string](#string) |  | Country code associated with this address ('US' or 'USA' for United States, for instance). |





<!-- end messages -->

<!-- end enums -->

<!-- end HasExtensions -->

<!-- end services -->


<a name="opencannabis/geo/Country.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## opencannabis/geo/Country.proto
Provides a structure to specify a country.


<a name="opencannabis.geo.Country"></a>

### Country
Specifies an independent nation state.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| code | [string](#string) |  | ISO country code. |





<!-- end messages -->

<!-- end enums -->

<!-- end HasExtensions -->

<!-- end services -->


<a name="opencannabis/geo/Distance.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## opencannabis/geo/Distance.proto
Describes geography-related models, specifically with regard to distances between two points.


<a name="opencannabis.geo.Distance"></a>

### Distance
Specifies a distance between two locations.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| estimate | [bool](#bool) |  | Specifies whether this distance is an estimate. |
| accuracy | [LocationAccuracy](#opencannabis.geo.LocationAccuracy) |  | Specifies the accuracy estimate for the distance values, if known. |
| unit | [DistanceUnit](#opencannabis.geo.DistanceUnit) |  | Specifies the unit of measurement for a location accuracy estimate. |






<a name="opencannabis.geo.DistanceValue"></a>

### DistanceValue
Specifies a single distance value.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| unit | [DistanceUnit](#opencannabis.geo.DistanceUnit) |  | Specifies the unit of measurement employed for this distance. |
| value | [double](#double) |  | Actual value. |






<a name="opencannabis.geo.LocationAccuracy"></a>

### LocationAccuracy
Represents an estimate of location accuracy.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| estimate | [bool](#bool) |  | Specifies whether this accuracy rating is an estimate. |
| value | [DistanceValue](#opencannabis.geo.DistanceValue) |  | Distance value for the accuracy specified. |





<!-- end messages -->


<a name="opencannabis.geo.DistanceUnit"></a>

### DistanceUnit
Enumeration of recognized units of distance.

| Name | Number | Description |
| ---- | ------ | ----------- |
| METERS | 0 | Distance in meters. |
| INCHES | 1 | Distance in inches. |
| FEET | 2 | Distance in feet. |
| MILLIMETERS | 3 | Distance in millimeters. |
| CENTIMETERS | 4 | Distance in centimeters. |
| KILOMETERS | 5 | Distance in kilometers. |
| MILES | 6 | Distance in miles. |


<!-- end enums -->

<!-- end HasExtensions -->

<!-- end services -->


<a name="opencannabis/geo/Geohash.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## opencannabis/geo/Geohash.proto
Defines objects in the OpenCannabis Geo module, that provide support for Geo-hashes.


<a name="opencannabis.geo.Geohash"></a>

### Geohash
Specifies a point or area on earth, in such a manner that a hash algorithm is applied, where digits can be removed to
"zoom-out" from the location.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| component | [string](#string) | repeated | Specifies geohash components. |
| elevation | [Distance](#opencannabis.geo.Distance) |  | Elevation of this point, if any. |
| accuracy | [Distance](#opencannabis.geo.Distance) |  | Accuracy rating attached to this point, if any. |





<!-- end messages -->

<!-- end enums -->

<!-- end HasExtensions -->

<!-- end services -->


<a name="opencannabis/geo/Point.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## opencannabis/geo/Point.proto
Provides a structure for specifying a specific point on the earth.


<a name="opencannabis.geo.MapCoordinate"></a>

### MapCoordinate
Specifies a map coordinate by tile and pixel locations.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| x | [uint32](#uint32) |  | `x` value for a map coordinate. |
| y | [uint32](#uint32) |  | `y` value for a map coordinate. |
| right | [uint32](#uint32) |  | `right` value for a map coordinate (tile `x`). |
| down | [uint32](#uint32) |  | `down` value for a map coordinate (tile `y`). |






<a name="opencannabis.geo.MapPosition"></a>

### MapPosition
Specifies a full map position, with space for all available points/coordinates.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| point | [Point](#opencannabis.geo.Point) |  | Geo-point (latitude/longitude) for the retail location. |
| tile | [MapCoordinate](#opencannabis.geo.MapCoordinate) |  | Tile/pixel coordinate for this location, using coordinates. |
| coordinate | [WorldCoordinate](#opencannabis.geo.WorldCoordinate) |  | Geo-coordinate (as a "world coordinate") for use with Google Maps. |
| zoom | [uint32](#uint32) |  | Zoom level for the map. |






<a name="opencannabis.geo.Point"></a>

### Point
Specifies a specific point on the earth, via a standard set of latitude/longitude coordinates, an elevation, and
optionally an accuracy rating. Accuracy and elevation are interpreted in 'feet' by default.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| latitude | [double](#double) |  | Latitude value of this point. |
| longitude | [double](#double) |  | Longitude value of this point. |
| elevation | [Distance](#opencannabis.geo.Distance) |  | Elevation of this point, if any. |
| accuracy | [Distance](#opencannabis.geo.Distance) |  | Accuracy rating attached to this point, if any. |






<a name="opencannabis.geo.WorldCoordinate"></a>

### WorldCoordinate
Specifies a world coordinate structure, which implements the Mercator Projection for use with Google Maps.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| right | [double](#double) |  | 'Right' value for a world coordinate. |
| down | [double](#double) |  | 'Down' value for a world coordinate. |
| elevation | [Distance](#opencannabis.geo.Distance) |  | Elevation of this point, if any. |
| accuracy | [Distance](#opencannabis.geo.Distance) |  | Accuracy rating attached to this point, if any. |





<!-- end messages -->

<!-- end enums -->

<!-- end HasExtensions -->

<!-- end services -->


<a name="opencannabis/geo/Location.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## opencannabis/geo/Location.proto
Provides structures for determining distance and accuracy, enumerates various units of measurement to express
distance.


<a name="opencannabis.geo.Location"></a>

### Location
Represents a physically addressable location in the real world.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [opencannabis.content.Name](#opencannabis.content.Name) |  | Name for this location, if applicable. |
| address | [Address](#opencannabis.geo.Address) |  | Address for this location, if applicable. |
| point | [Point](#opencannabis.geo.Point) |  | Geo-point (latitude/longitude) for this location. |
| accuracy | [LocationAccuracy](#opencannabis.geo.LocationAccuracy) |  | Specifies the accuracy estimate, if known. |





<!-- end messages -->

<!-- end enums -->

<!-- end HasExtensions -->

<!-- end services -->


<a name="opencannabis/geo/USState.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## opencannabis/geo/USState.proto
Enumerates the various States of the United States of America

<!-- end messages -->


<a name="opencannabis.geo.usa.USState"></a>

### USState
Enumerates United States member states and territories by their full name and abbreviation.

| Name | Number | Description |
| ---- | ------ | ----------- |
| UNSPECIFIED | 0 | Default: Unspecified. |
| AL | 1 | State of Alabama. |
| ALABAMA | 1 |  |
| AK | 2 | State of Alaska. |
| ALASKA | 2 |  |
| AZ | 3 | State of Arizona. |
| ARIZONA | 3 |  |
| AR | 4 | State of Arkansas. |
| ARKANSAS | 4 |  |
| CA | 5 | State of California. |
| CALIFORNIA | 5 |  |
| CO | 6 | State of Colorado. |
| COLORADO | 6 |  |
| CT | 7 | State of Connecticut. |
| CONNECTICUT | 7 |  |
| DE | 8 | State of Delaware. |
| Delaware | 8 |  |
| DC | 9 | Washington, District of Columbia (DC). |
| DISTRICT_OF_COLUMBIA | 9 |  |
| FL | 10 | State of Florida. |
| FLORIDA | 10 |  |
| GA | 11 | State of Georgia. |
| GEORGIA | 11 |  |
| HI | 12 | State of Hawaii. |
| HAWAII | 12 |  |
| ID | 13 | State of Idaho. |
| IDAHO | 13 |  |
| IL | 14 | State of Illinois. |
| ILLINOIS | 14 |  |
| IN | 15 | State of Indiana. |
| INDIANA | 15 |  |
| IA | 16 | State of Iowa. |
| IOWA | 16 |  |
| KS | 17 | State of Kansas. |
| KANSAS | 17 |  |
| KY | 18 | State of Kentucky. |
| KENTUCKY | 18 |  |
| LA | 19 | State of Loisiana. |
| LOISIANA | 19 |  |
| ME | 20 | State of Maine. |
| MAINE | 20 |  |
| MD | 21 | State of Maryland. |
| MARYLAND | 21 |  |
| MA | 22 | State of Massachusetts. |
| MASSACHUSETTS | 22 |  |
| MI | 23 | State of Michigan. |
| MICHIGAN | 23 |  |
| MN | 24 | State of Minnesota. |
| MINNESOTA | 24 |  |
| MS | 25 | State of Mississippi. |
| MISSISSIPPI | 25 |  |
| MO | 26 | State of Missouri. |
| MISSOURI | 26 |  |
| MT | 27 | State of Montana. |
| MONTANA | 27 |  |
| NE | 28 | State of Nebraska. |
| NEBRASKA | 28 |  |
| NV | 29 | State of Nevada. |
| NEVADA | 29 |  |
| NH | 30 | State of New Hampshire. |
| NEW_HAMPSHIRE | 30 |  |
| NJ | 31 | State of New Jersey. |
| NEW_JERSEY | 31 |  |
| NM | 32 | State of New Mexico. |
| NEW_MEXICO | 32 |  |
| NY | 33 | State of New York. |
| NEW_YORK | 33 |  |
| NC | 34 | State of North Carolina. |
| NORTH_CAROLINA | 34 |  |
| ND | 35 | State of North Dakota. |
| NORTH_DAKOTA | 35 |  |
| OH | 36 | State of Ohio. |
| OHIO | 36 |  |
| OK | 37 | State of Oklahoma. |
| OKLAHOMA | 37 |  |
| OR | 38 | State of Oregon. |
| OREGON | 38 |  |
| PA | 39 | State of Pennsylvania. |
| PENNSYLVANIA | 39 |  |
| RI | 40 | State of Rhode Island. |
| RHODE_ISLAND | 40 |  |
| SC | 41 | State of South Carolina. |
| SOUTH_CAROLINA | 41 |  |
| SD | 42 | State of South Dakota. |
| SOUTH_DAKOTA | 42 |  |
| TN | 43 | State of Tennessee. |
| TENNESSEE | 43 |  |
| TX | 44 | State of Texas. |
| TEXAS | 44 |  |
| UT | 45 | State of Utah. |
| UTAH | 45 |  |
| VT | 46 | State of Vermont. |
| VERMONT | 46 |  |
| VA | 47 | State of Virginia. |
| VIRGINIA | 47 |  |
| WA | 48 | State of Washington. |
| WASHINGTON | 48 |  |
| WV | 49 | State of West Virginia. |
| WEST_VIRGINIA | 49 |  |
| WI | 50 | State of Wisconsin. |
| WISCONSIN | 50 |  |
| WYOMING | 51 | State of Wyoming. |
| WY | 51 |  |


<!-- end enums -->

<!-- end HasExtensions -->

<!-- end services -->


<a name="opencannabis/geo/Province.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## opencannabis/geo/Province.proto
Provides structures for specifying a provincial area of a country.


<a name="opencannabis.geo.Province"></a>

### Province
Specifies a US or non-US province.


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| state | [usa.USState](#opencannabis.geo.usa.USState) |  | US state, specified by enumerated ID. |
| province | [string](#string) |  | Generic province reference, by name. |





<!-- end messages -->

<!-- end enums -->

<!-- end HasExtensions -->

<!-- end services -->



---

Copyright &copy; 2021, OpenCannabis Authors. All rights reserved. Shared and released under
[GNU GPLv3 License](https://www.gnu.org/licenses/gpl-3.0.en.html). For more details regarding licensing, please see the
`LICENSE.txt` file distributed with the OpenCannabis Protocol Sources.
