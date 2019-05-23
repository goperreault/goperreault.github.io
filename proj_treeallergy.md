---
title: Tree Allergy 
layout: default
---
## Location of trees in Mississauga
Small project that maps four species of trees (ash, birch, oak and willow) in the city of Mississauga. 

# Static map
![Ash trees map](./Ash_trees.jpeg)

# Interactive map 
<div id="mapid" style="width: 600px; height: 400px">
      <script>
            var mymap = L.map('mapid').setView([43.588, -79.648], 11);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
                  maxZoom: 18,
                  id: 'mapbox.streets',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(mymap);
            function onEachFeature(feature, layer) {
                    if (feature.properties && feature.properties.popupContent) {
                    layer.bindPopup(feature.properties.popupContent);
                }
            } 
            var geojsonMarkerOptions = {
                  radius: 2,
                  fillColor: "#ff7800",
                  color: "#000",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            }; 
            $.getJSON("Tree_3857_ash.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerOptions);
                        // onEachFeature:onEachFeature
                        }    
                  }).addTo(mymap);
            });
     </script>
</div>
[Homepage](./index.html)