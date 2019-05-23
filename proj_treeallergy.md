---
title: Tree Allergy 
layout: default
---
## Location of trees in Mississauga
Small project that maps four species of trees (ash, birch, oak and willow) in the city of Mississauga. It uses to city's Open data tree inventory catalog. The goal is to identify where each species is located in the city.

# Static maps
![Ash trees map](./Ash_trees.jpeg)
<img src="Ash_trees.jpeg" alt="Ash Trees" width="200"/>

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
            var geojsonMarkerAsh = {
                  radius: 2,
                  fillColor: "#259ff0",
                  color: "#000",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            }; 
            var geojsonMarkerBirch = {
                  radius: 2,
                  fillColor: "#729b6f",
                  color: "#000",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            };
            var geojsonMarkerOak = {
                  radius: 2,
                  fillColor: "#a47158",
                  color: "#000",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            };
            var geojsonMarkerWillow = {
                  radius: 2,
                  fillColor: "#85b66f",
                  color: "#000",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            };
            $.getJSON("Tree_3857_ash.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerAsh);
                        // onEachFeature:onEachFeature
                        }    
                  }).addTo(mymap);
            });
            $.getJSON("Tree_3857_birch.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerBirch);
                        // onEachFeature:onEachFeature
                        }    
                  }).addTo(mymap);
            });
            $.getJSON("Tree_3857_oak.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerOak);
                        // onEachFeature:onEachFeature
                        }    
                  }).addTo(mymap);
            });
            $.getJSON("Tree_3857_willow.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerWillow);
                        // onEachFeature:onEachFeature
                        }    
                  }).addTo(mymap);
            });
     </script>
</div>
[Homepage](./index.html)
