---
title: Tree Allergy
layout: default
---
# Trees and pollen allergies in Mississauga
Small project to help with my seasonal pollen allergies. It maps four tree species from which I am allergic to. It uses to city of Mississauga's Open data tree inventory catalog to extract all ash, birch, oak and willow species. The goal of the project is to identify where each species is located within the city and compare to start/end of allergy seasons.

## Static maps
### Large image
![Ash trees map](./Trees.jpeg)

## Interactive map
<div id="mapid" style="width: 700px; height: 600px">
      <script>
            var mymap = L.map('mapid').setView([43.599, -79.648], 11);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: 'City-owned Tree Inventory - MississaugaData, 03/04/2019 <br>Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
                  maxZoom: 18,
                  id: 'mapbox.streets',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(mymap);
            var geojsonMarkerAsh = {
                  radius: 3,
                  fillColor: "#259ff0",
                  color: "#000",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            };
            var geojsonMarkerBirch = {
                  radius: 3,
                  fillColor: "#729b6f",
                  color: "#000",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            };
            var geojsonMarkerOak = {
                  radius: 3,
                  fillColor: "#a47158",
                  color: "#000",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            };
            var geojsonMarkerWillow = {
                  radius: 3,
                  fillColor: "#f45f42",
                  color: "#000",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            };
            function getColor(d) {
                  return d === 'Ash'  ? "#259ff0" :
                  d === 'Birch'  ? "#729b6f" :
                  d === 'Oak' ? "#a47158" :
                 "#f45f42";
            }
            function forEachFeature(feature, layer) {
                var popupContent =  feature.properties.BOTDESC;
                layer.bindPopup(popupContent);
                //layer.bindTooltip(popupContent);
            }
            $.getJSON("Tree_3857_ash.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerAsh);
                        },
                        onEachFeature: forEachFeature
                  }).addTo(mymap);
            });
            $.getJSON("Tree_3857_birch.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerBirch);
                        },
                        onEachFeature: forEachFeature
                  }).addTo(mymap);
            });
            $.getJSON("Tree_3857_oak.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerOak);
                        },
                        onEachFeature: forEachFeature
                  }).addTo(mymap);
            });
            $.getJSON("Tree_3857_willow.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerWillow);
                        },
                        onEachFeature: forEachFeature
                  }).addTo(mymap);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (map) {
                  var div = L.DomUtil.create('div', 'info legend'),
                  labels = ['<strong>Trees</strong>'],
                  categories = ['Ash','Birch','Oak','Willow'];
                  for (var i = 0; i < categories.length; i++) {
                    div.innerHTML += labels.push(
                      '<i class="circle" style="background:' + getColor(categories[i]) + '"></i> ' +
                      (categories[i] ? categories[i] + '<br>' : '+')
                    );
                  }
                  div.innerHTML = labels.join('<br>');
                  return div;
             };
             legend.addTo(mymap);
     </script>
</div>
[Homepage](./index.html)
