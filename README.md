D3.Leaflet
===
takes geojson or topojson and uses d3 (possibly with the help of topojson) to add it to a leaflet map as a layer. Bassed off [http://bost.ocks.org/mike/leaflet/](this example)

not sure if it actually solves any problem besides helping me learn d3.

api:

```js
L.d3(data,options);
//or
new L.D3(data,options);
```

where data is either a url to geojson or topojson data or it can be an object, and options include:

* "topojson" which is false if not topojson or the name of the topojson object you want.
* "pathClass" the class your paths should have, this defaults to "path" and can be a string or a function which recieves the feature and returns the path string.
* "type" whether d3 should download and treat it as json, csv, xml, text, tsv, html.  Considering how this library makes some pretty strong assumes re it being json I'd not touch this.  Forget I put this here. 

Your going to want to add css styles manually, note that by default csv closes paths and fills them for you if you don't specify "fill:none;" Also I'd avoid styling "path" as that will effect all leaflet paths, including regular ones made inside leaflet. 