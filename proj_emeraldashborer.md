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
<div id="mapidtreecwp" style="width: 700px; height: 950px">
      <script>
            var mymaptreecwp = L.map('mapidtreecwp').setView([43.580222, -79.662720], 16);
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
             var legend2 = L.control({position: 'bottomleft'});
             legend2.onAdd = function (map) {
                   var div = L.DomUtil.create('div', 'info legend');
                   labels = ['<strong>Trees</strong>'];
                   div.innerHTML += '<i class="circle" style="background: #a8f8a8"></i><span>Accolate Elm</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #780000"></i><span>American Elm</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #fe0001"></i><span>Ash SPP.</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #08f808"></i><span>Austrian Pine</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #c0feff"></i><span>Basswood Linden</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #880888"></i><span>Bur Oak</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #78a2ff"></i><span>Colorado Blue Spruce</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #96c2ff"></i><span>Colorado Spruce</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #00a001"></i><span>Columnar Norway Maple</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #fee601"></i><span>Common Zelkova</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #fecc01"></i><span>Deadoo</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #feb401"></i><span>Eastern White Cedar</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #fe9a01"></i><span>False Cyprus</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #0c0c0d"></i><span>Glenleven Linden</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #363636"></i><span>Honey Locust</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #877878"></i><span>Iron Wood</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #9494a1"></i><span>Ivory Silk Japanese Lilac</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #d67ad0"></i><span>Littleleaf Linden</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #705039"></i><span>Norway Maple</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #705039"></i><span>Red Maple</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #705039"></i><span>Red Oak</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #705039"></i><span>Scotch Pine</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #705039"></i><span>Shagbark Hickory</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #705039"></i><span>Silver Maple</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #705039"></i><span>Stump</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #705039"></i><span>Sugar Maple</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #705039"></i><span>Trembling Poplar</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #705039"></i><span>White Oak</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #705039"></i><span>White Pine</span><br>';
                   div.innerHTML += '<i class="circle" style="background: #705039"></i><span>White Spruce</span><br>';
                   return div
              };
             legend2.addTo(mymaptreecwp);
     </script>
</div>
