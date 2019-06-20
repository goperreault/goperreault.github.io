---
title: Tree Allergy
layout: default
---
# Trees and pollen allergies in Mississauga
A project to help with my seasonal pollen allergies. It maps the four tree species from which I get the worse allergic reaction during springtime. It uses to city of Mississauga's Open data tree inventory catalog to extract all of the ash, birch, oak and willow species. The goal of the project is to identify where each species is located within the city and compare to start/end of allergy seasons.

## Pollen season
According to the [Aerobiology Research Laboratories](http://www.pollenexperts.ca/toronto-ontario/), all four tree pollens start in April and lasts until late May to early June, the exception being willow that ends earlier in May. Additional research shows that rising temperatures affect pollen season, as shown in [Lewis H Ziska et al's study of the northern hemisphere](https://www.sciencedirect.com/science/article/pii/S2542519619300154?via%3Dihub&for-guid=a3a12ea2-bd65-e711-b65f-90b11c343abd&utm_source=usatoday-Climate%20Point&utm_medium=email&utm_campaign=narrative&utm_term=article_body#!).

[//]: <> ## Static maps
[//]: <> The follow maps show the distribution of each trees species in the city.
[//]: <> ![Ash trees map](./Ash_trees.jpeg)
[//]: <> ![Birch trees map](./Birch_trees.jpeg)
[//]: <> ![Oak trees map](./Oak_trees.jpeg)
[//]: <> ![Willow trees map](./Willow_trees.jpeg)

## Interactive map
The follow map is an interactive map that shows all four tree species in Mississauga.
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
[Homepage](./index.html)
