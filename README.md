&lt;open-map&gt; element &lt;/open-map&gt;
==========================================

Make Open Street Maps using declarative Polymer web components. To get started read the [&lt;open-doc&gt;&lt;/open-doc&gt;] or checkout the [&lt;open-demo&gt;&lt;/open-demo&gt;].


Tech
-----------

`<open-map></open-map>` use:
* [Mapbox] - Awesome library for use Open Maps
* [Polymer] - Awesome framework for web components.
* [maki] - Native icons for mapbox. `<open-marker icon="{'icon':'restaurant'}"></open-marker>`

Use guide
--------------
##### Install open-map component using [bower].

```bash
$ bower install open-map#master

```

##### Configure Polymer and the new component.

```html
<head>
	<script src="../platform/platform.js"></script>
	<link rel="import" href="../open-map/open-map.html">
	<style>
		html, body {
			margin: 0;
			height: 100%;
		}
		leaflet-map {
			height: 100%;
		}
	</style>
</head>
<body unresolved>
	<open-map id="map"
		zoom="15"
		latitude="38.908847"
		mapID="villeda.c4c63d13"
		longitude="1.433900">
		<open-marker label="School Bus" latitude="38.909847"
			longitude="1.435900"
			icon="{'icon':'bus', 'markerColor':'#ff0000'}"
			draggable="true">
		</open-marker>
		<open-marker id="me" label="Me"
				icon="{'icon':'pitch', 'markerColor':'#000'}" >
		</open-marker>
	</open-map>
	<script type="text/javascript">
		(function(document, navigator){
			'use strict';
			var me = document.querySelector('#me');
			navigator.geolocation.watchPosition(function(pos) {
				me.latitude = pos.coords.latitude;
				me.longitude = pos.coords.longitude;
			});
		}(document, navigator));
	</script>
</body>
```

![Preview][1]

# &lt;open-map&gt;&lt;/open-map&gt;

Attributes
----------

| Attribute       | Type    | Default            |
| --------------- | :-----: | -----------------: |
| `mapID`         | String  | gnurub.j3ee3mk2    |
| `geolocationUI` | Boolean | false              |
| `fullscreenUI`  | Boolean | false              |
| `zoom`          | Number  | 10                 |
| `disableZoomUI` | Boolean | false              |
| `zoomable`      | Boolean | true               |
| `latitude`      | Float   | 38.867847507701114 |
| `longitude`     | Float   | 1.3109779357910156 |
| `maxZoom`       | Number  | 16                 |
| `minZoom`       | Number  | 1                  |
| `maxBounds`     | Array   | null               |



Methods
--------

| Method          | Function               |
| --------------- | :--------------------: |
| `clear`         | Remove all markers.    |

Events
------
| Event                | Function                       |
| -------------------- | :----------------------------: |
| `open-map-ready`     | Fired when map is ready        |
| `open-map-zoomened`  | Fired on zoom change           |

# &lt;open-marker&gt;&lt;/open-marker&gt;

Attributes
----------
| Attribute       | Type    | Default            |
| --------------- | :-----: | -----------------: |
| `latitude`      | Float   | null               |
| `longitude`     | Float   | null               |
| `icon`          | Object  | null               |
| `label`         | String  | null               |


##### Params for Icon
| Param             | Type    | Default   |
| ----------------- | :-----: | --------: |
| `icon`            | String  |  null     |
| `iconUrl`         | URL     |  null     |
| `iconRetinaUrl`   | URL     |  null     |
| `iconSize`        | Array   | [35, 45]  |
| `iconAnchor`      | Array   | [17, 42]  |
| `popupAnchor`     | Array   | [1, -32]  |
| `shadowUrl`       | URL     | null      |
| `shadowRetinaUrl` | URL     | null      |
| `shadowSize`      | Array   | [36, 16]  |
| `shadowAnchor`    | Array   | [10, 12]  |
| `markerColor`     | String  | '#ff0000' |


Methods
-------

Events
------
| Even                |   Function                                           	|
| ------------------- | :----------------------------:												|
| `dblclick-marker`   | Fired when double clicked     										    |
| `click-marker`      | Fired when clicked.          												  |
| `move-marker`       | Fired when the marker is moved via latitude/longitude |
| `dragstart-marker`  | Fired when drag starts.        												|
| `dragend-marker`    | Fired when drag ends.          												|
| `drag-marker`       | Fired when dragged.            												|
| `remove-marker`     | Fired when marker is removed.  												|
| `popupopen-marker`  | Fired when the popup is opened.												|
| `popupclose-marker` | Fired when the popup is closed.												|

# &lt;open-search&gt;&lt;/open-search&gt;

Properties
----------
| Property        | Type    | Funtion                            |
| --------------- | :-----: | ---------------------------------: |
| `result`        | Object  | Returns an object with the results |

Attributes
----------
| Attribute       | Type    | Function                           |
| --------------- | :-----: | ---------------------------------: |
| `query`         | Array   | Array that contains the querys     |
| `accessToken`   | String  | String whit the access token       |

Events
------
| Even                    |   Function                               |
| ----------------------- | :-------------------------------------:	 |
| `open-search-results`   | Fired it when the result is available.   |

Personalize the map
-------------------
You can personalize the map using the [MapBoxEditor] or [MapBoxStudio], introduce your map id in the attribute `mapID`.

License
-------
MIT


[&lt;open-demo&gt;&lt;/open-demo&gt;]:https://ruben96.github.io/open-map/components/open-map/demo.html
[&lt;open-doc&gt;&lt;/open-doc&gt;]:https://ruben96.github.io/open-map
[Polymer]:http://www.polymer-project.org/
[MapBoxEditor]:https://www.mapbox.com/editor
[MapBoxStudio]:https://www.mapbox.com/mapbox-studio/
[Mapbox]:https://www.mapbox.com/
[maki]:https://www.mapbox.com/maki/
[bower]:http://bower.io/
[1]:http://pix.toile-libre.org/upload/original/1410995143.png
