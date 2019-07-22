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
<div id="mapidtreecwp" style="width: 700px; height: 850px">
      <script>
            var mymaptreecwp = L.map('mapidtreecwp').setView([43.580222, -79.661820], 16);
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
                    radius: 3,
                    fillColor: "#a8f8a8",
                    weight: 2,
                    opacity: 0.5,
                    color: "#a8f8a8",
                    fillOpacity: 0.5
                  }
                  case 'AMERICAN ELM': return {
                    radius: 3,
                    fillColor: "#780000",
                    weight: 2,
                    opacity: 0.5,
                    color: "#780000",
                    fillOpacity: 0.5
                  }
                  case 'ASH SPP.': return {
                    radius: 3,
                    fillColor: "#fe0001",
                    weight: 2,
                    opacity: 0.5,
                    color: "#fe0001",
                    fillOpacity: 0.5
                  }
                  case 'AUSTRIAN PINE': return {
                    radius: 3,
                    fillColor: "#08f808",
                    weight: 2,
                    opacity: 0.5,
                    color: "#08f808",
                    fillOpacity: 0.5
                  }
                  case 'BASSWOOD LINDEN': return {
                    radius: 3,
                    fillColor: "#c0feff",
                    weight: 2,
                    opacity: 0.5,
                    color: "#c0feff",
                    fillOpacity: 0.5
                  }
                  case 'BUR OAK': return {
                    radius: 3,
                    fillColor: "#880888",
                    weight: 2,
                    opacity: 0.5,
                    color: "#880888",
                    fillOpacity: 0.5
                  }
                  case 'COLORADO BLUE SPRUCE': return {
                    fillColor: "#78a2ff",
                    weight: 2,
                    opacity: 0.5,
                    color: "#78a2ff",
                    fillOpacity: 0.5
                  }
                  case 'COLORADO SPRUCE': return {
                    fillColor: "#96c2ff",
                    weight: 2,
                    opacity: 0.5,
                    color: "#96c2ff",
                    fillOpacity: 0.5
                  }
                  case 'COLUMNAR NORWAY MAPLE': return {
                    fillColor: "#00a001",
                    weight: 2,
                    opacity: 0.5,
                    color: "#00a001",
                    fillOpacity: 0.5
                  }
                  case 'COMMON ZELKOVA': return {
                    fillColor: "#fee601",
                    weight: 2,
                    opacity: 0.5,
                    color: "#fee601",
                    fillOpacity: 0.5
                  }
                  case 'DEADOO': return {
                    fillColor: "#fecc01",
                    weight: 2,
                    opacity: 0.5,
                    color: "#fecc01",
                    fillOpacity: 0.5
                  }
                  case 'EASTERN WHITE CEDAR': return {
                    fillColor: "#fe9a01",
                    weight: 2,
                    opacity: 0.5,
                    color: "#fe9a01",
                    fillOpacity: 0.5
                  }
                  case 'FALSE CYPRUS': return {
                    fillColor: "#feb401",
                    weight: 2,
                    opacity: 0.5,
                    color: "#feb401",
                    fillOpacity: 0.5
                  }
                  case 'GLENLEVEN LINDEN': return {
                    fillColor: "#0c0c0d",
                    weight: 2,
                    opacity: 0.5,
                    color: "#0c0c0d",
                    fillOpacity: 0.5
                  }
                  case 'HONEY LOCUST': return {
                    fillColor: "#363636",
                    weight: 2,
                    opacity: 0.5,
                    color: "#363636",
                    fillOpacity: 0.5
                  }
                  case 'IRON WOOD': return {
                    fillColor: "#877878",
                    weight: 2,
                    opacity: 0.5,
                    color: "#877878",
                    fillOpacity: 0.5
                  }
                  case 'IVORY SILK JAPANESE LILAC': return {
                    fillColor: "#9494a1",
                    weight: 2,
                    opacity: 0.5,
                    color: "#9494a1",
                    fillOpacity: 0.5
                  }
                  case 'LITTLELEAF LINDEN': return {
                    fillColor: "#d67ad0",
                    weight: 2,
                    opacity: 0.5,
                    color: "#d67ad0",
                    fillOpacity: 0.5
                  }
                  case 'NORWAY MAPLE': return {
                    fillColor: "#705039",
                    weight: 2,
                    opacity: 0.5,
                    color: "#705039",
                    fillOpacity: 0.5
                  }
                  case 'RED MAPLE': return {
                    fillColor: "#705039",
                    weight: 2,
                    opacity: 0.5,
                    color: "#705039",
                    fillOpacity: 0.5
                  }
                  case 'RED OAK': return {
                    fillColor: "#705039",
                    weight: 2,
                    opacity: 0.5,
                    color: "#705039",
                    fillOpacity: 0.5
                  }
                  case 'SCOTCH PINE': return {
                    fillColor: "#705039",
                    weight: 2,
                    opacity: 0.5,
                    color: "#705039",
                    fillOpacity: 0.5
                  }
                  case 'SHAGBARK HICKORY': return {
                    fillColor: "#705039",
                    weight: 2,
                    opacity: 0.5,
                    color: "#705039",
                    fillOpacity: 0.5
                  }
                  case 'SILVER MAPLE': return {
                    fillColor: "#705039",
                    weight: 2,
                    opacity: 0.5,
                    color: "#705039",
                    fillOpacity: 0.5
                  }
                  case 'STUMP': return {
                    fillColor: "#705039",
                    weight: 2,
                    opacity: 0.5,
                    color: "#705039",
                    fillOpacity: 0.5
                  }
                  case 'SUGAR MAPLE': return {
                    fillColor: "#705039",
                    weight: 2,
                    opacity: 0.5,
                    color: "#705039",
                    fillOpacity: 0.5
                  }
                  case 'TREMBLING POPLAR': return {
                    fillColor: "#705039",
                    weight: 2,
                    opacity: 0.5,
                    color: "#705039",
                    fillOpacity: 0.5
                  }
                  case 'WHITE OAK': return {
                    fillColor: "#705039",
                    weight: 2,
                    opacity: 0.5,
                    color: "#705039",
                    fillOpacity: 0.5
                  }
                  case 'WHITE PINE': return {
                    fillColor: "#705039",
                    weight: 2,
                    opacity: 0.5,
                    color: "#705039",
                    fillOpacity: 0.5
                  }
                  case 'WHITE SPRUCE': return {
                    fillColor: "#705039",
                    weight: 2,
                    opacity: 0.5,
                    color: "#705039",
                    fillOpacity: 0.5
                  }
                  default: return{
                    fillColor: "#ffffff",
                    weight: 2,
                    opacity: 0.5,
                    color: "#ffffff",
                    fillOpacity: 0.5
                  }
                }
            }
            function getTreeColor(d) {
              switch(d){
                case 'ACCOLATE ELM': return  "#a8f8a8";
                case 'Accolate Elm': return  "#a8f8a8";
                case 'AMERICAN ELM': return "#780000";
                case 'American Elm': return "#780000";
                case 'ASH SPP.': return "#fe0001";
                case 'Ash SPP.': return "#fe0001";
                case 'AUSTRIAN PINE': return "#08f808";
                case 'Austrian Pine': return "#08f808";
                case 'BASSWOOD LINDEN': return "#c0feff";
                case 'Basswood Linden': return "#c0feff";
                case 'BUR OAK': return "#880888";
                case 'Bur Oak': return "#880888";
                case 'Colorado Blue Spruce': return "#78a2ff";
                case 'COLORADO BLUE SPRUCE': return "#78a2ff";
                case 'COLORADO SPRUCE': return "#96c2ff";
                case 'Colorado Spruce': return "#96c2ff";
                case 'COLUMNAR NORWAY MAPLE': return "#00a001";
                case 'Columnar Norway Maple': return "#00a001";
                case 'COMMON ZELKOVA': return "#fee601";
                case 'Common Zelkova': return "#fee601";
                case 'DEADOO': return "#fecc01";
                case 'Deadoo': return "#fecc01";
                case 'EASTERN WHITE CEDAR': return "#fe9a01";
                case 'Eastern White Cedar': return "#fe9a01";
                case 'FALSE CYPRUS': return "#feb401";
                case 'False Cyprus': return "#feb401";
                case 'GLENLEVEN LINDEN': return "#0c0c0d";
                case 'Glenleven Linden': return "#0c0c0d";
                case 'HONEY LOCUST': return "#363636";
                case 'Honey Locust': return "#363636";
                case 'IRON WOOD': return "#877878";
                case 'Iron Wood': return "#877878";
                case 'IVORY SILK JAPANESE LILAC': return "#9494a1";
                case 'Ivory Silk Japanese Lilac': return "#9494a1";
                case 'LITTLELEAF LINDEN': return "#d67ad0";
                case 'Littleleaf Linden': return "#d67ad0";
                case 'NORWAY MAPLE': return "#705039";
                case 'Norway Maple': return "#705039";
                case 'RED MAPLE': return "#705039";
                case 'Red Maple': return "#705039";
                case 'RED OAK': return "#705039";
                case 'Red Oak': return "#705039";
                case 'SCOTCH PINE': return "#705039";
                case 'Scotch Pine': return "#705039";
                case 'SHAGBARK HICKORY': return "#705039";
                case 'Shagbark Hickory': return "#705039";
                case 'SILVER MAPLE': return "#705039";
                case 'Silver Maple': return "#705039";
                case 'STUMP': return "#705039";
                case 'Stump': return "#705039";
                case 'SUGAR MAPLE': return "#705039";
                case 'Sugar Maple': return "#705039";
                case 'TREMBLING POPLAR': return "#705039";
                case 'Trembling Poplar': return "#705039";
                case 'WHITE OAK': return "#705039";
                case 'White Oak': return "#705039";
                case 'WHITE PINE': return "#705039";
                case 'White Pine': return "#705039";
                case 'WHITE SPRUCE': return "#705039";
                case 'White Spruce': return "#705039";
                default: return '#ffffff'
              }

            }
            function forEachFeature(feature, layer) {
                var popupContent =  feature.properties.BOTDESC;
                layer.bindPopup(popupContent);
                //layer.bindTooltip(popupContent);
            }
            $.getJSON("geo_layers/Tree_3857_creditviewwoods.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, {fillColor: getTreeColor(feature.properties.BOTDESC),
                                                      radius: 3,
                                                      weight: 2,
                                                      opacity: 0.5,
                                                      color: "#000000",
                                                      fillOpacity: 0.5}
                                              );
                        },

                        onEachFeature: forEachFeature
                  }).addTo(mymaptreecwp);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (map) {
                  var div = L.DomUtil.create('div', 'info legend'),
                  labels = ['<strong>Trees</strong>'],
                  categories = ['ACCOLATE ELM','AMERICAN ELM','ASH SPP.','AUSTRIAN PINE','BASSWOOD LINDEN','BUR OAK','COLORADO BLUE SPRUCE','COLORADO SPRUCE','COLUMNAR NORWAY MAPLE','COMMON ZELKOVA','DEADOO','EASTERN WHITE CEDAR','FALSE CYPRUS','GLENLEVEN LINDEN','HONEY LOCUST','IRON WOOD','IVORY SILK JAPANESE LILAC','LITTLELEAF LINDEN','NORWAY MAPLE','RED MAPLE','RED OAK','SCOTCH PINE','SHAGBARK HICKORY','SILVER MAPLE','STUMP','SUGAR MAPLE','TREMBLING POPLAR','WHITE OAK','WHITE PINE','WHITE SPRUCE'];
                  categoriesL = ['Accolate Elm','American Elm','Ash SPP.','Austrian Pine','Basswood Linden','Bur Oak','Colorado Blue Spruce','Colorado Spruce','Columnar Norway Maple','Common Zelkova','Deadoo','Eastern White Cedar','False Cyprus','Glenleven Linden','Honey Locust','Iron Wood','Ivory Silk Japanese Lilac','Littleleaf Linden','Norway Maple','Red Maple','Red Oak','Scotch Pine','Shagbark Hickory','Silver Maple','Stump','Sugar Maple','Trembling Poplar','White Oak','White Pine','White Spruce'];
                  for (var i = 0; i < categoriesL.length; i++) {
                    div.innerHTML += labels.push(
                      '<i class="circle" style="background:' + getTreeColor(categoriesL[i]) + '"></i> ' +
                      (categoriesL[i] ? categoriesL[i] + '<br>' : '+')
                    );
                  }

                  div.innerHTML = labels.join('<br>');
                  return div;
             };
             legend.addTo(mymaptreecwp);
     </script>
</div>
