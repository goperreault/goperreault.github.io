---
title: Grand Paris Express
layout: default
---
# The Grand Paris Express around Paris, Line 15
A project that draws Line 15, a subset of the larger Grand Paris Express, around the city of Paris. This larger infrastructure project consist of [four new automated metro lines and the extension of existing metro lines to connect key areas around Paris](https://www.societedugrandparis.fr/info/grand-paris-express-largest-transport-project-europe-1061).
## Line 15 and existing Métro lines
The following map shows Line 15 in comparison to the existing Métro lines. It also draws 500 meter buffers around each of the stations, showing the extent of coverage of the metro within a geographically small area. 
<div id="mapidmetro" style="width: 700px; height: 500px">
      <script>
            var mapmetro = L.map('mapidmetro').setView([48.854908, 2.387671], 11);
            L.tileLayer('https://api.mapbox.com/styles/v1/{id}/tiles/{z}/{x}/{y}?access_token={accessToken}', {
                  attribution: 'Offre transport de la RATP - RATP, 22/05/2019, sous license ODbL<br>Map data &copy; © <a href="https://www.mapbox.com/about/maps/">Mapbox</a> © <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a> <strong><a href="https://www.mapbox.com/map-feedback/" target="_blank">Improve this map</a></strong>',
                  maxZoom: 18,
                  id: 'mapbox/light-v10',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(mapmetro)
            var geojsonMetroStops = {
                  radius: 3,
                  fillColor: "#a90f32",
                  color: "#a90f32",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            };
            function linestyle(feature) {
                return {
                  fillColor: "#a90f32",
                  weight: 2,
                  opacity: 1,
                  color: "#a90f32",
                  fillOpacity: 0.7
                };
            }
            function metrolinestyle(feature) {
                return {
                  fillColor: "#3294db",
                  weight: 2,
                  opacity: 0.9,
                  color: "#3294db",
                  fillOpacity: 0.9
                };
            }
            function polystyle(feature) {
                return {
                  fillColor: "#c6c6c6",
                  weight: 2,
                  opacity: 0.5,
                  color: "#a90f32",
                  fillOpacity: 0.5
                };
            }
            function forEachFeature(feature, layer) {
                var popupContent =  "Station:</br>" + feature.properties.nom;
                //layer.bindPopup(popupContent);
                layer.bindTooltip(popupContent);
            }
            $.getJSON("geo_layers/MetroAllLines.geojson",function(data){
                  L.geoJson(data, {
                      style: metrolinestyle
                  }).addTo(mapmetro);
            });
            $.getJSON("geo_layers/ligne15_ligne.geojson",function(data){
                  L.geoJson(data, {
                      style: linestyle
                  }).addTo(mapmetro);
            });
            $.getJSON("geo_layers/ligne15_stops.geojson",function(data){
                  L.geoJson(data, {
                      pointToLayer: function (feature, latlng){
                          return L.circleMarker(latlng, geojsonMetroStops);
                      },
                      onEachFeature: forEachFeature
                  }).addTo(mapmetro);
            });
            $.getJSON("geo_layers/buff500_merge_dis.geojson",function(data){
                  L.geoJson(data, {
                      style: polystyle
                  }).addTo(mapmetro);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (mapmetro) {
                  var div = L.DomUtil.create('div', 'info legend');/*,
                  labels = ['<strong>Metro</strong>'],
                  categories = ['Line 5'];
                  labels.push(categories);
                  div.innerHTML = labels.join('<br>'); */
                  /*div.innerHTML += "<h4>Metro</h4>";*/
                  div.innerHTML += '<i class="circle" style="background: #a90f32"></i><span>Line 15 Stations</span><br>';
                  div.innerHTML += '<i class="polyline" style="background: #a90f32"></i><span>Line 15</span><br>';
                  div.innerHTML += '<i class="polyline" style="background: #3294db"></i><span>Existing Métro Lines</span><br>';
                  return div
            }
            legend.addTo(mapmetro);
     </script>
</div>

## Line 15 and existing RER lines
The following map shows Line 15 in comparison to the existing RER lines.
<div id="mapidrer" style="width: 700px; height: 500px">
      <script>
            var maprer = L.map('mapidrer').setView([48.854908, 2.387671], 11);
            L.tileLayer('https://api.mapbox.com/styles/v1/{id}/tiles/{z}/{x}/{y}?access_token={accessToken}', {
                  attribution: 'Offre transport de la RATP - RATP, 22/05/2019, sous license ODbL<br>Tracés du réseau de transport ferré dIle-de-France -<br>Ile-de-France Mobilités, 23/11/2018, Open licence<br>Map data &copy; © <a href="https://www.mapbox.com/about/maps/">Mapbox</a> © <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a> <strong><a href="https://www.mapbox.com/map-feedback/" target="_blank">Improve this map</a></strong>',
                  maxZoom: 18,
                  id: 'mapbox/light-v10',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(maprer)
            var geojsonMetroStops = {
                  radius: 3,
                  fillColor: "#a90f32",
                  color: "#a90f32",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            };
            function linestyle(feature) {
                return {
                  fillColor: "#a90f32",
                  weight: 2,
                  opacity: 1,
                  color: "#a90f32",
                  fillOpacity: 0.7
                };
            }
            function rerlinestyle(feature) {
                return {
                  fillColor: "#4eba77",
                  weight: 3,
                  opacity: 0.9,
                  color: "#4eba77",
                  fillOpacity: 0.7
                };
            }
            function forEachFeature(feature, layer) {
                var popupContent =  "Station:</br>" + feature.properties.nom;
                //layer.bindPopup(popupContent);
                layer.bindTooltip(popupContent);
            }
            $.getJSON("geo_layers/RERAllLines.geojson",function(data){
                  L.geoJson(data, {
                      style: rerlinestyle
                  }).addTo(maprer);
            });
            $.getJSON("geo_layers/ligne15_ligne.geojson",function(data){
                  L.geoJson(data, {
                      style: linestyle
                  }).addTo(maprer);
            });
            $.getJSON("geo_layers/ligne15_stops.geojson",function(data){
                  L.geoJson(data, {
                      pointToLayer: function (feature, latlng){
                          return L.circleMarker(latlng, geojsonMetroStops);
                      },
                      onEachFeature: forEachFeature
                  }).addTo(maprer);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (maprer) {
                  var div = L.DomUtil.create('div', 'info legend');/*,
                  labels = ['<strong>Metro</strong>'],
                  categories = ['Line 5'];
                  labels.push(categories);
                  div.innerHTML = labels.join('<br>'); */
                  /*div.innerHTML += "<h4>Metro</h4>";*/
                  div.innerHTML += '<i class="circle" style="background: #a90f32"></i><span>Line 15 Stations</span><br>';
                  div.innerHTML += '<i class="polyline" style="background: #a90f32"></i><span>Line 15</span><br>';
                  div.innerHTML += '<i class="polylinerer" style="background: #4eba77"></i><span>Existing RER Lines</span><br>';
                  return div
            }

            legend.addTo(maprer);
     </script>
</div>
## Line 15 and existing Transilien lines
The following map shows Line 15 in comparison to the existing Transilien lines, that end at the major railway stations in Paris.
<div id="mapidtransilien" style="width: 700px; height: 500px">
      <script>
            var maptransilien = L.map('mapidtransilien').setView([48.854908, 2.387671], 11);
            L.tileLayer('https://api.mapbox.com/styles/v1/{id}/tiles/{z}/{x}/{y}?access_token={accessToken}', {
                  attribution: 'Tracés du réseau de transport ferré dIle-de-France -<br>Ile-de-France Mobilités, 23/11/2018, Open licence<br>Map data &copy; © <a href="https://www.mapbox.com/about/maps/">Mapbox</a> © <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a> <strong><a href="https://www.mapbox.com/map-feedback/" target="_blank">Improve this map</a></strong>',
                  maxZoom: 18,
                  id: 'mapbox/light-v10',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(maptransilien)
            var geojsonMetroStops = {
                  radius: 3,
                  fillColor: "#a90f32",
                  color: "#a90f32",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            };
            function linestyle(feature) {
                return {
                  fillColor: "#a90f32",
                  weight: 2,
                  opacity: 1,
                  color: "#a90f32",
                  fillOpacity: 0.7
                };
            }
            function transilienlinestyle(feature) {
                return {
                  fillColor: "#4eba77",
                  weight: 3,
                  opacity: 0.5,
                  color: "#4b2587",
                  fillOpacity: 0.9
                };
            }
            function forEachFeature(feature, layer) {
                var popupContent =  "Station:</br>" + feature.properties.nom;
                //layer.bindPopup(popupContent);
                layer.bindTooltip(popupContent);
            }
            $.getJSON("geo_layers/TransilienAllLines.geojson",function(data){
                  L.geoJson(data, {
                      style: transilienlinestyle
                  }).addTo(maptransilien);
            });
            $.getJSON("geo_layers/ligne15_ligne.geojson",function(data){
                  L.geoJson(data, {
                      style: linestyle
                  }).addTo(maptransilien);
            });
            $.getJSON("geo_layers/ligne15_stops.geojson",function(data){
                  L.geoJson(data, {
                      pointToLayer: function (feature, latlng){
                          return L.circleMarker(latlng, geojsonMetroStops);
                      },
                      onEachFeature: forEachFeature
                  }).addTo(maptransilien);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (maptransilien) {
                  var div = L.DomUtil.create('div', 'info legend');/*,
                  labels = ['<strong>Metro</strong>'],
                  categories = ['Line 5'];
                  labels.push(categories);
                  div.innerHTML = labels.join('<br>'); */
                  /*div.innerHTML += "<h4>Metro</h4>";*/
                  div.innerHTML += '<i class="circle" style="background: #a90f32"></i><span>Line 15 Stations</span><br>';
                  div.innerHTML += '<i class="polyline" style="background: #a90f32"></i><span>Line 15</span><br>';
                  div.innerHTML += '<i class="polylinerer" style="background: #4b2587"></i><span>Existing Transilien Lines</span><br>';
                  return div
            }

            legend.addTo(maptransilien);
     </script>
</div>
## Line 15 and defunct circular line, La Petite Ceinture
The following map shows Line 15 in comparison to La Petite Ceinture, the city of Paris' defunct circular line that operated passenger services until the [1930s](https://www.paris.fr/petiteceinture). The map was made to compare the old circular railway to the future metro. It displays the extent of the urban area around Paris for which La Petite Ceinture would not serve if put back into service today.
<div id="mapidceinture" style="width: 700px; height: 500px">
      <script>
            var mapceinture = L.map('mapidceinture').setView([48.854908, 2.387671], 11);
            L.tileLayer('https://api.mapbox.com/styles/v1/{id}/tiles/{z}/{x}/{y}?access_token={accessToken}', {
                  attribution: 'La Petite Ceinture - <a href="https://www.apur.org/en">Apur</a> 2017<br>Offre transport de la RATP - RATP, 22/05/2019, sous license ODbL<br>Map data &copy; © <a href="https://www.mapbox.com/about/maps/">Mapbox</a> © <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a> <strong><a href="https://www.mapbox.com/map-feedback/" target="_blank">Improve this map</a></strong>',
                  maxZoom: 18,
                  id: 'mapbox/light-v10',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(mapceinture)
            var geojsonMetroStops = {
                  radius: 3,
                  fillColor: "#a90f32",
                  color: "#a90f32",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            };
            function linestyle(feature) {
                return {
                  fillColor: "#a90f32",
                  weight: 2,
                  opacity: 1,
                  color: "#a90f32",
                  fillOpacity: 0.7
                };
            }
            function ceinturelinestyle(feature) {
                return {
                  fillColor: "#222323",
                  weight: 3,
                  opacity: 0.5,
                  color: "#222323",
                  fillOpacity: 0.9
                };
            }
            function forEachFeature(feature, layer) {
                var popupContent =  feature.properties.nom;
                //layer.bindPopup(popupContent);
                layer.bindTooltip(popupContent);
            }
            function quinzeLigneForEachFeature(feature, layer) {
                var popupContent =  "Station:</br>" + feature.properties.name;
                //layer.bindPopup(popupContent);
                layer.bindTooltip(popupContent);
            }
            $.getJSON("geo_layers/petiteceintureline.geojson",function(data){
                  L.geoJson(data, {
                      style: ceinturelinestyle

                  }).addTo(mapceinture);
            });
            $.getJSON("geo_layers/ligne15_ligne.geojson",function(data){
                  L.geoJson(data, {
                      style: linestyle

                  }).addTo(mapceinture);
            });
            $.getJSON("geo_layers/ligne15_stops.geojson",function(data){
                  L.geoJson(data, {
                      pointToLayer: function (feature, latlng){
                          return L.circleMarker(latlng, geojsonMetroStops);
                      },
                      onEachFeature: forEachFeature
                  }).addTo(mapceinture);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (mapceinture) {
                  var div = L.DomUtil.create('div', 'info legend');/*,
                  labels = ['<strong>Metro</strong>'],
                  categories = ['Line 5'];
                  labels.push(categories);
                  div.innerHTML = labels.join('<br>'); */
                  /*div.innerHTML += "<h4>Metro</h4>";*/
                  div.innerHTML += '<i class="circle" style="background: #a90f32"></i><span>Line 15 Stations</span><br>';
                  div.innerHTML += '<i class="polyline" style="background: #a90f32"></i><span>Line 15</span><br>';
                  div.innerHTML += '<i class="polyline" style="background: #222323"></i><span>La Petite Ceinture</span><br>';
                  return div
            }

            legend.addTo(mapceinture);
     </script>
</div>
[//]: <> [Homepage](./index.html)
