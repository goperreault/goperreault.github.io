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
I had visited the site in 2017 where I noticed the effects of the removal in the forested areas.

The following map shows the current trees located in Creditview Woods Park based on the city's tree data inventory. The next map shows the Ash trees in the area.
<div id="mapidtreecwp" style="width: 700px; height: 600px">
      <script>
            var mymaptreecwp = L.map('mapidtreecwp').setView([43.580222, -79.662720], 16);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: 'City-owned Tree Inventory - MississaugaData, 03/04/2019 <br>Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
                  maxZoom: 18,
                  id: 'mapbox.streets',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(mymaptreecwp);
            function getTreeColor(d) {
              switch(d){
                case 'ACCOLATE ELM': return  "#a81787";
                case 'AMERICAN ELM': return "#20102d";
                case 'ASH SPP.': return "#33c423";
                case 'AUSTRIAN PINE': return "#f2ef72";
                case 'BASSWOOD LINDEN': return "#b7216c";
                case 'BUR OAK': return "#f14a54";
                case 'COLORADO BLUE SPRUCE': return "#426c6f";
                case 'COLORADO SPRUCE': return "#51286c";
                case 'COLUMNAR NORWAY MAPLE': return "#a50dd8";
                case 'COMMON ZELKOVA': return "#0c0ced";
                case 'DEADOO': return "#c98d69";
                case 'EASTERN WHITE CEDAR': return "#378a35";
                case 'FALSE CYPRUS': return "#52fbe5";
                case 'GLENLEVEN LINDEN': return "#105b76";
                case 'HONEY LOCUST': return "#659bcb";
                case 'IRON WOOD': return "#e3a3b7";
                case 'IVORY SILK JAPANESE LILAC': return "#724632";
                case 'LITTLELEAF LINDEN': return "#95b308";
                case 'NORWAY MAPLE': return "#f11a3a";
                case 'RED MAPLE': return "#ea08d3";
                case 'RED OAK': return "#e1ec64";
                case 'SCOTCH PINE': return "#8765a6";
                case 'SHAGBARK HICKORY': return "#af1545";
                case 'SILVER MAPLE': return "#8fbc60";
                case 'STUMP': return "#7f1a64";
                case 'SUGAR MAPLE': return "#63bb17";
                case 'TREMBLING POPLAR': return "#edb824";
                case 'WHITE OAK': return "#2bdbd8";
                case 'WHITE PINE': return "#f41556";
                case 'WHITE SPRUCE': return "#705039";
                default: return '#ffffff'
              }

            }
            function forEachFeature(feature, layer) {
                var popupContent =  feature.properties.BOTDESC;
                //layer.bindPopup(popupContent);
                layer.bindTooltip(popupContent);
            }
            $.getJSON("geo_layers/Tree_3857_creditviewwoods.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, {fillColor: getTreeColor(feature.properties.BOTDESC),
                                                      radius: 3,
                                                      weight: 1,
                                                      opacity: 1,
                                                      color: "#000000",
                                                      fillOpacity: 0.8}
                                              );
                        },

                        onEachFeature: forEachFeature
                  }).addTo(mymaptreecwp);
            });
            $.getJSON("geo_layers/Tree_3857_ash_creditviewwoods.geojson",function(data){
                  L.geoJson(data, {
                        pointToLayer: function (feature, latlng) {
                        return L.circleMarker(latlng, {fillColor: getTreeColor(feature.properties.BOTDESC),
                                                      radius: 5,
                                                      weight: 1,
                                                      opacity: 1,
                                                      color: "#000000",
                                                      fillOpacity: 0.8}
                                              );
                        },

                        onEachFeature: forEachFeature
                  }).addTo(mymaptreecwp);
            });
             var legend2 = L.control({position: 'bottomleft'});
             legend2.onAdd = function (map) {
                   var div = L.DomUtil.create('div', 'info legend');
                   labels = ['<strong>Trees</strong>'];
                   div.innerHTML += '<i class="circle" style="background: #a81787"></i><span>Accolate Elm</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #20102d"></i><span>American Elm</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #33c423"></i><span>Ash SPP.</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #f2ef72"></i><span>Austrian Pine</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #b7216c"></i><span>Basswood Linden</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #f14a54"></i><span>Bur Oak</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #426c6f"></i><span>Colorado Blue Spruce</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #51286c"></i><span>Colorado Spruce</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #a50dd8"></i><span>Columnar Norway Maple</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #0c0ced"></i><span>Common Zelkova</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #c98d69"></i><span>Deadoo</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #378a35"></i><span>Eastern White Cedar</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #52fbe5"></i><span>False Cyprus</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #105b76"></i><span>Glenleven Linden</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #659bcb"></i><span>Honey Locust</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #e3a3b7"></i><span>Iron Wood</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #724632"></i><span>Ivory Silk Japanese Lilac</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #95b308"></i><span>Littleleaf Linden</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #f11a3a"></i><span>Norway Maple</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #ea08d3"></i><span>Red Maple</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #e1ec64"></i><span>Red Oak</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #8765a6"></i><span>Scotch Pine</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #af1545"></i><span>Shagbark Hickory</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #8fbc60"></i><span>Silver Maple</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #7f1a64"></i><span>Stump</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #63bb17"></i><span>Sugar Maple</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #edb824"></i><span>Trembling Poplar</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #2bdbd8"></i><span>White Oak</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #f41556"></i><span>White Pine</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #705039"></i><span>White Spruce</span><br>';
                   return div
              };
             legend2.addTo(mymaptreecwp);
     </script>
</div>
