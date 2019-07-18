---
title: Emerald Ash Borer
layout: default
---
# Emerald Ash Borer in Mississauga
During the summer of 2017 I had the opportunity to particpate in a research project that involved the emerald ash borer infestation in Mississauga. The research was possible thanks to Dr. Yuhong He from the Department of Geography at the University of Toronto Mississauga. Data was provided by the City of Mississauga included removed ash trees from 2014 to 2017, remaining ash trees as of 2017 and treated ash trees from 2016 to 2017. The research I performed looked at the removal of ash trees to locate the highest concentration within the city.

## Removed Tree Density
Map showing the highest areas of ash tree removals. Two areas, located near the centre of the city, had the most removals.
![EAB Density Map](./EABRemovalDensity_1.jpg)

## Highest Density Site: Creditview Woods Park
Map showing the site with the highest density of removed trees. In total, 874 ash trees were removed due to poor health of the trees. As seen on the map, most of the trees were located within the forested area.
![EAB Site Removal](./MissSite1_1.jpg)

## Current Tree Status
During the summer of 2019 I will be visiting Creditview Woods Park to observe the current status of the trees. I had visited the site in 2017 where I noticed the effects of the removal in the forested areas.

The following map shows the current trees located in Creditview Woods Park based on the city's tree data inventory.
<div id="mapidtreecwp" style="width: 700px; height: 600px">
      <script>
            var mymaptreecwp = L.map('mapidtreecwp').setView([43.580222, -79.661720], 16);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: 'City-owned Tree Inventory - MississaugaData, 03/04/2019 <br>Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
                  maxZoom: 18,
                  id: 'mapbox.streets',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(mymaptreecwp);
            var geojsonMarkerCWP = {
                  radius: 3,
                  fillColor: "#259ff0",
                  color: "#000",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            };
            function treecwstyle(feature) {
                switch (feature.properties.BOTDESC){
                  case 'ACCOLATE ELM': return {
                    fillColor: "#a8f8a8",
                    weight: 2,
                    opacity: 0.5,
                    color: "#a8f8a8",
                    fillOpacity: 0.5
                  };
                  case 'Bureau': return {
                    fillColor: "#780000",
                    weight: 2,
                    opacity: 0.5,
                    color: "#780000",
                    fillOpacity: 0.5
                  }
                  case 'Commerciale': return {
                    fillColor: "#fe0001",
                    weight: 2,
                    opacity: 0.5,
                    color: "#fe0001",
                    fillOpacity: 0.5
                  }
                  case 'Golf': return {
                    fillColor: "#08f808",
                    weight: 2,
                    opacity: 0.5,
                    color: "#08f808",
                    fillOpacity: 0.5
                  }
                  case 'Hydrographie': return {
                    fillColor: "#c0feff",
                    weight: 2,
                    opacity: 0.5,
                    color: "#c0feff",
                    fillOpacity: 0.5
                  }
                  case 'Industrie': return {
                    fillColor: "#880888",
                    weight: 2,
                    opacity: 0.5,
                    color: "#880888",
                    fillOpacity: 0.5
                  }
                  case 'Institution économique': return {
                    fillColor: "#78a2ff",
                    weight: 2,
                    opacity: 0.5,
                    color: "#78a2ff",
                    fillOpacity: 0.5
                  }
                  case 'Institution non-économique': return {
                    fillColor: "#96c2ff",
                    weight: 2,
                    opacity: 0.5,
                    color: "#96c2ff",
                    fillOpacity: 0.5
                  }
                  case 'Parc ou espace vert': return {
                    fillColor: "#00a001",
                    weight: 2,
                    opacity: 0.5,
                    color: "#00a001",
                    fillOpacity: 0.5
                  }
                  case 'Residence 1 logement': return {
                    fillColor: "#fee601",
                    weight: 2,
                    opacity: 0.5,
                    color: "#fee601",
                    fillOpacity: 0.5
                  }
                  case 'Residence ou condo 2-4 logements': return {
                    fillColor: "#fecc01",
                    weight: 2,
                    opacity: 0.5,
                    color: "#fecc01",
                    fillOpacity: 0.5
                  }
                  case 'Residence ou condo 25+ logements': return {
                    fillColor: "#fe9a01",
                    weight: 2,
                    opacity: 0.5,
                    color: "#fe9a01",
                    fillOpacity: 0.5
                  }
                  case 'Residence ou condo 5-24 logements': return {
                    fillColor: "#feb401",
                    weight: 2,
                    opacity: 0.5,
                    color: "#feb401",
                    fillOpacity: 0.5
                  }
                  case 'Rue ou ruelle': return {
                    fillColor: "#0c0c0d",
                    weight: 2,
                    opacity: 0.5,
                    color: "#0c0c0d",
                    fillOpacity: 0.5
                  }
                  case 'Stationnement': return {
                    fillColor: "#363636",
                    weight: 2,
                    opacity: 0.5,
                    color: "#363636",
                    fillOpacity: 0.5
                  }
                  case 'Terrain vacant': return {
                    fillColor: "#877878",
                    weight: 2,
                    opacity: 0.5,
                    color: "#877878",
                    fillOpacity: 0.5
                  }
                  case 'Utilité publique': return {
                    fillColor: "#9494a1",
                    weight: 2,
                    opacity: 0.5,
                    color: "#9494a1",
                    fillOpacity: 0.5
                  }
                  case 'Zone aéroportuaire': return {
                    fillColor: "#d67ad0",
                    weight: 2,
                    opacity: 0.5,
                    color: "#d67ad0",
                    fillOpacity: 0.5
                  }
                  case 'Zone ferroviaire': return {
                    fillColor: "#705039",
                    weight: 2,
                    opacity: 0.5,
                    color: "#705039",
                    fillOpacity: 0.5
                  }
                }
            }
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
            $.getJSON("geo_layers/Tree_3857_creditviewwoods.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, treecwstyle);
                        },
                        onEachFeature: forEachFeature
                  }).addTo(mymaptreecwp);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (map) {
                  var div = L.DomUtil.create('div', 'info legend'),
                  labels = ['<strong>Trees</strong>'],
                  categories = ['Trees'];
                  for (var i = 0; i < categories.length; i++) {
                    div.innerHTML += labels.push(
                      '<i class="circle" style="background:' + getColor(categories[i]) + '"></i> ' +
                      (categories[i] ? categories[i] + '<br>' : '+')
                    );
                  }
                  div.innerHTML = labels.join('<br>');
                  return div;
             };
             legend.addTo(mymaptrecwp);
     </script>
</div>
