---
title: Tree Allergy
layout: default
---
# Trees and pollen allergies in Mississauga
A project to help with my seasonal pollen allergies. It maps the four tree species from which I get the worse allergic reaction during springtime. It uses the City of Mississauga's Open data tree inventory catalog to extract all of the ash, birch, oak and willow species. The goal of the project is to identify where each species is located within the the Lisgar neighbourhood, in particular the trail located alongside a creek.

## Pollen season
According to the [Aerobiology Research Laboratories](http://www.pollenexperts.ca/toronto-ontario/), all four tree pollens start in April and lasts until late May to early June, the exception being willow that ends earlier in May. Through anecdotal evidence I can confirm that pollen season lasts from late April to mid June.

[//]: <> ## Static maps
[//]: <> The follow maps show the distribution of each trees species in the city.
[//]: <> ![Ash trees map](./Ash_trees.jpeg)
[//]: <> ![Birch trees map](./Birch_trees.jpeg)
[//]: <> ![Oak trees map](./Oak_trees.jpeg)
[//]: <> ![Willow trees map](./Willow_trees.jpeg)


## All Trees
The following map shows all four tree species in Mississauga.
<div id="mapid" style="width: 700px; height: 600px">
      <script>
            var mymap = L.map('mapid').setView([43.599, -79.648], 11);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: 'City-owned Tree Inventory - MississaugaData, 03/04/2019 <br>Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
                  maxZoom: 18,
                  id: 'mapbox/streets-v11',
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
            $.getJSON("geo_layers/Tree_3857_ash.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerAsh);
                        },
                        onEachFeature: forEachFeature
                  }).addTo(mymap);
            });
            $.getJSON("geo_layers/Tree_3857_birch.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerBirch);
                        },
                        onEachFeature: forEachFeature
                  }).addTo(mymap);
            });
            $.getJSON("geo_layers/Tree_3857_oak.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerOak);
                        },
                        onEachFeature: forEachFeature
                  }).addTo(mymap);
            });
            $.getJSON("geo_layers/Tree_3857_willow.geojson",function(data){
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

## Ash map
The following map shows all ash tree species that are located within 100 meters of a city park.
<div id="mapidash" style="width: 700px; height: 600px">
      <script>
            var mymapash = L.map('mapidash').setView([43.599, -79.648], 11);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: 'City-owned Tree Inventory - MississaugaData, 03/04/2019 <br>Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
                  maxZoom: 18,
                  id: 'mapbox/streets-v11',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(mymapash);
            var geojsonMarkerAsh = {
                  radius: 3,
                  fillColor: "#259ff0",
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
            $.getJSON("geo_layers/Tree_3857_ash_park.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerAsh);
                        },
                        onEachFeature: forEachFeature
                  }).addTo(mymapash);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (map) {
                  var div = L.DomUtil.create('div', 'info legend'),
                  labels = ['<strong>Trees</strong>'],
                  categories = ['Ash'];
                  for (var i = 0; i < categories.length; i++) {
                    div.innerHTML += labels.push(
                      '<i class="circle" style="background:' + getColor(categories[i]) + '"></i> ' +
                      (categories[i] ? categories[i] + '<br>' : '+')
                    );
                  }
                  div.innerHTML = labels.join('<br>');
                  return div;
             };
             legend.addTo(mymapash);
     </script>
</div>

## Birch map
The following map shows all birch tree species that are located within 100 meters of a city park.
<div id="mapidbirch" style="width: 700px; height: 600px">
      <script>
            var mymapbirch = L.map('mapidbirch').setView([43.599, -79.648], 11);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: 'City-owned Tree Inventory - MississaugaData, 03/04/2019 <br>Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
                  maxZoom: 18,
                  id: 'mapbox.streets',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(mymapbirch);
            var geojsonMarkerBirch = {
                  radius: 3,
                  fillColor: "#729b6f",
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
            $.getJSON("geo_layers/Tree_3857_birch_park.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerBirch);
                        },
                        onEachFeature: forEachFeature
                  }).addTo(mymapbirch);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (map) {
                  var div = L.DomUtil.create('div', 'info legend'),
                  labels = ['<strong>Trees</strong>'],
                  categories = ['Birch'];
                  for (var i = 0; i < categories.length; i++) {
                    div.innerHTML += labels.push(
                      '<i class="circle" style="background:' + getColor(categories[i]) + '"></i> ' +
                      (categories[i] ? categories[i] + '<br>' : '+')
                    );
                  }
                  div.innerHTML = labels.join('<br>');
                  return div;
             };
             legend.addTo(mymapbirch);
     </script>
</div>

## Oak map
The following map shows all oak tree species that are located within 100 meters of a city park.
<div id="mapidoak" style="width: 700px; height: 600px">
      <script>
            var mymapoak = L.map('mapidoak').setView([43.599, -79.648], 11);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: 'City-owned Tree Inventory - MississaugaData, 03/04/2019 <br>Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
                  maxZoom: 18,
                  id: 'mapbox.streets',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(mymapoak);
            var geojsonMarkerOak = {
                  radius: 3,
                  fillColor: "#a47158",
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
            $.getJSON("geo_layers/Tree_3857_oak_park.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerOak);
                        },
                        onEachFeature: forEachFeature
                  }).addTo(mymapoak);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (map) {
                  var div = L.DomUtil.create('div', 'info legend'),
                  labels = ['<strong>Trees</strong>'],
                  categories = ['Oak'];
                  for (var i = 0; i < categories.length; i++) {
                    div.innerHTML += labels.push(
                      '<i class="circle" style="background:' + getColor(categories[i]) + '"></i> ' +
                      (categories[i] ? categories[i] + '<br>' : '+')
                    );
                  }
                  div.innerHTML = labels.join('<br>');
                  return div;
             };
             legend.addTo(mymapoak);
     </script>
</div>

## Willow map
The following map shows all willow tree species that are located within 100 meters of a city park.
<div id="mapidwillow" style="width: 700px; height: 600px">
      <script>
            var mymapwillow = L.map('mapidwillow').setView([43.599, -79.648], 11);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: 'City-owned Tree Inventory - MississaugaData, 03/04/2019 <br>Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
                  maxZoom: 18,
                  id: 'mapbox.streets',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(mymapwillow);
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
            $.getJSON("geo_layers/Tree_3857_willow_park.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, geojsonMarkerWillow);
                        },
                        onEachFeature: forEachFeature
                  }).addTo(mymapwillow);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (map) {
                  var div = L.DomUtil.create('div', 'info legend'),
                  labels = ['<strong>Trees</strong>'],
                  categories = ['Willow'];
                  for (var i = 0; i < categories.length; i++) {
                    div.innerHTML += labels.push(
                      '<i class="circle" style="background:' + getColor(categories[i]) + '"></i> ' +
                      (categories[i] ? categories[i] + '<br>' : '+')
                    );
                  }
                  div.innerHTML = labels.join('<br>');
                  return div;
             };
             legend.addTo(mymapwillow);
     </script>
</div>
<!--
## Lisgar neighbourhood
The Lisgar neighbourhood in Mississauga is home to the Lisgar Meadow Brook Trail, a 4.7km trail that starts at Buttonbush Park, follows a creek and ends at Osprey Marsh. By visualizing the location of the trees along the trail, it becomes useful to know which areas of the trail to possibly avoid during the springtime. A parallel route exists using Lisgar Drive and Rosehurst Drive, where the trees were also mapped to compare both the trail and road.
-->
[//]: <> [Homepage](./index.html)
