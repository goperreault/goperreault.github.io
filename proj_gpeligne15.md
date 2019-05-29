---
title: Grand Paris Express
layout: default
---
# The Grand Paris Express around Paris, Line 15
Small project that draws the intended ligne around the city of Paris.
<div id="mapid" style="width: 600px; height: 400px">
      <script>
            var map = L.map('mapid').setView([48.854908, 2.387671], 11);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
                  maxZoom: 18,
                  id: 'mapbox.light',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(map)
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
            function forEachFeature(feature, layer) {
                var popupContent =  "Station:</br>" + feature.properties.nom;
                layer.bindPopup(popupContent);
            }
            $.getJSON("ligne15_ligne.geojson",function(data){
                  L.geoJson(data, {
                      style: linestyle
                  }).addTo(map);
            });
            $.getJSON("ligne15_stops.geojson",function(data){
                  L.geoJson(data, {
                      onEachFeature: forEachFeature,
                      pointToLayer: function (feature, latlng){
                          return L.circleMarker(latlng, geojsonMetroStops);
                      }
                  }).addTo(map);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (map) {
                  var div = L.DomUtil.create('div', 'info legend');/*,
                  labels = ['<strong>Metro</strong>'],
                  categories = ['Line 5'];
                  labels.push(categories);
                  div.innerHTML = labels.join('<br>'); */
                  div.innerHTML += "<h4>Metro</h4>";
                  div.innerHTML += '<i class="polyline" style="background: #a90f32"></i><span>Line 15</span><br>';
                  div.innerHTML += '<i class="circle" style="background: #a90f32"></i><span>Line 15 Stations</span><br>';
                  return div
            }

            legend.addTo(map);
     </script>
</div>
[Homepage](./index.html)
