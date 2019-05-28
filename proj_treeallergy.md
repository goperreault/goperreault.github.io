---
title: Tree Allergy
layout: default
---
# Location of trees in Mississauga
Small project that maps four tree species (ash, birch, oak and willow) in the city of Mississauga. It uses to city's Open data tree inventory catalog. The goal is to identify where each species is located in the city.

## Static maps
### Large image
![Ash trees map](./Ash_trees.jpeg)
### Small image
<img src="Ash_trees.jpeg" alt="Ash Trees" width="200"/>

## Interactive map
<div id="mapid" style="width: 600px; height: 400px">
      <script>
            var mymap = L.map('mapid').setView([43.588, -79.648], 11);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
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
            $.getJSON("Tree_3857_ash.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerAsh);
                        }
                  }).addTo(mymap);
            });
            $.getJSON("Tree_3857_birch.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerBirch);
                        }
                  }).addTo(mymap);
            });
            $.getJSON("Tree_3857_oak.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerOak);
                        }
                  }).addTo(mymap);
            });
            $.getJSON("Tree_3857_willow.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerWillow);
                        }
                  }).addTo(mymap);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (map) {
                  var div = L.DomUtil.create('div', 'info legend');/*,
                  labels = ['<strong>Trees</strong>'],
                  categories = ['Ash','Birch','Oak','Willow'];
                  for (var i = 0; i < categories.length; i++) {
                    div.innerHTML += labels.push(
                      '<i class="circle" style="background:' + getColor(categories[i]) + '"></i> ' +
                      (categories[i] ? categories[i] + '<br>' : '+')
                    );
                  }
                  div.innerHTML = labels.join('<br>');*/
                  div.innerHTML += "<h4>Trees</h4>";
                  div.innerHTML += '<i class="circle" style="background: #259ff0"></i><span>Ash</span><br>';
                  div.innerHTML += '<i class="circle" style="background: #729b6f"></i><span>Birch</span><br>';
                  div.innerHTML += '<i class="circle" style="background: #a47158"></i><span>Oak</span><br>';
                  div.innerHTML += '<i style="background: #f45f42"></i><span>Willow</span><br>';
                  return div;
             };
             legend.addTo(mymap);
     </script>
</div>
[Homepage](./index.html)
