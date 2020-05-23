---
title: Mirabel Airport
layout: default
---

# Mirabel Airport Land Coverage
A project that shows the coverage of the Mirabel Airport.

## Land
Map that shows the required land that was expropriated for the construction of the airport. This map is based on a source found through a TVA news report. The map shows the large extent of the land centered around the Autoroute 15 and Autoroute 50 interchange, a key interchange that never saw its intended traffic use over the years. In fact, Autoroute 50 was only partially completed in 2xxx (source).
<div id="mapidmirabel" style="width: 700px; height: 500px">
      <script>
            var mapmirabel = L.map('mapidmirabel').setView([45.657400, -74.075657], 10);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: '<a href="https://www.tvanouvelles.ca/2015/10/06/des-images-de-laeroport-rarement-vues">TVA Nouvelles/Des images de laéroport rarement vues</a><br>Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
                  maxZoom: 18,
                  id: 'mapbox.streets',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(mapmirabel)
            var geojsonMirabel = {
                  fillColor: "#a90f32",
                  color: "#a90f32",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            };
            function polystyle(feature) {
                return {
                  fillColor: "#a90f32",
                  weight: 2,
                  opacity: 0.5,
                  color: "#a90f32",
                  fillOpacity: 0.5
                };
            }
            $.getJSON("geo_layers/mirabelairportpoly.geojson",function(data){
                  L.geoJson(data, {
                      style: polystyle
                  }).addTo(mapmirabel);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (mapmirabel) {
                  var div = L.DomUtil.create('div', 'info legend');/*,
                  labels = ['<strong>Metro</strong>'],
                  categories = ['Line 5'];
                  labels.push(categories);
                  div.innerHTML = labels.join('<br>'); */
                  /*div.innerHTML += "<h4>Metro</h4>";*/
                  div.innerHTML += '<i class="polygon" style="background: #a90f32"></i><span>Mirabel Aiport Land</span><br>';
                  return div
            }
            legend.addTo(mapmirabel);
     </script>
</div>

## Current Landuse
Map that shows how the land is used based on 2016 data. According to the [city's website](https://ville.mirabel.qc.ca/ville/a-propos-de-mirabel), Mirabel is home to 55 020 residents, where a large portion of the land being for agricultural uses. The bright green area clearly shows how much of the land is currently classified as agricultural.
<div id="mapidmirabelclass" style="width: 700px; height: 500px">
      <script>
            var mapmirabelclass = L.map('mapidmirabelclass').setView([45.657400, -74.185657], 10);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: '<a href="http://cmm.qc.ca/donnees-et-territoire/observatoire-grand-montreal/produits-cartographiques/donnees-georeferencees/">Utilisation du sol, 2016, Communauté Métropolitaine de Montréal</a><br>Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
                  maxZoom: 18,
                  id: 'mapbox.streets',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(mapmirabelclass)
            var geojsonMirabel = {
                  fillColor: "#a90f32",
                  color: "#a90f32",
                  weight: 1,
                  opacity: 1,
                  fillOpacity: 0.8
            };
            function mirastyle(feature) {
                switch (feature.properties.class){
                  case 'Agricole': return {
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
            function forEachFeature(feature, layer) {
                var popupContent =  feature.properties.class;
                layer.bindPopup(popupContent);
                //layer.bindTooltip(popupContent);
            }
            $.getJSON("geo_layers/classification_74005-US-2016.geojson",function(data){
                  L.geoJson(data, {
                      style: mirastyle

                  }).addTo(mapmirabelclass);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (mapmirabelclass) {
                  var div = L.DomUtil.create('div', 'info legend');
                  div.innerHTML += '<i class="polygon" style="background: #a8f8a8"></i><span>Agricole</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #780000"></i><span>Bureau</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #fe0001"></i><span>Commerciale</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #08f808"></i><span>Golf</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #c0feff"></i><span>Hydrographie</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #880888"></i><span>Industrie</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #78a2ff"></i><span>Institution économique</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #96c2ff"></i><span>Institution non-économique</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #00a001"></i><span>Parc ou espace vert</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #fee601"></i><span>Résidence 1 logement</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #fecc01"></i><span>Residence ou condo 2-4 logements</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #feb401"></i><span>Residence ou condo 5-24 logements</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #fe9a01"></i><span>Residence ou condo 25+ logements</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #0c0c0d"></i><span>Rue ou ruelle</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #363636"></i><span>Stationnement</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #877878"></i><span>Terrain vacant</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #9494a1"></i><span>Utilité publique</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #d67ad0"></i><span>Zone aéroportuaire</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #705039"></i><span>Zone ferroviaire</span><br>';
                  return div
            }
            legend.addTo(mapmirabelclass);
     </script>
</div>

## Urban vs Non-urban
Map that shows how the non-urban land use dominates the area. The urban area measures 103,999 square kilometres whereas the non-urban area measures 382,392 square kilometres, making the non-urban cover 78% of the land. As shown in the previous map, agricultural land makes up the non-urban uses. This echoes the thought that most of the expropriated land shown in the first map was not utilized as the aiport did not grow to its intended size. 
<div id="mapidmirabelurban" style="width: 700px; height: 500px">
      <script>
            var mapmirabelurban = L.map('mapidmirabelurban').setView([45.657400, -74.075657], 10);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: '<a href="http://cmm.qc.ca/donnees-et-territoire/observatoire-grand-montreal/produits-cartographiques/donnees-georeferencees/">Utilisation du sol, 2016, Communauté Métropolitaine de Montréal</a><br>Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
                  maxZoom: 18,
                  id: 'mapbox.streets',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(mapmirabelurban)
            function miraurbanstyle(feature) {
                return {
                    fillColor: "#b7484b",
                    weight: 2,
                    opacity: 0.5,
                    color: "#b7484b",
                    fillOpacity: 0.5
                  };
            }
            function miranonurbanstyle(feature) {
                return {
                    fillColor: "#ffb947",
                    weight: 2,
                    opacity: 0.5,
                    color: "#ffb947",
                    fillOpacity: 0.5
                  };
            }
            function forEachFeature(feature, layer) {
                var popupContent =  feature.properties.class;
                layer.bindPopup(popupContent);
                //layer.bindTooltip(popupContent);
            }
            $.getJSON("geo_layers/classification_74005-US-2016_urban.geojson",function(data){
                  L.geoJson(data, {
                      style: miraurbanstyle
                  }).addTo(mapmirabelurban);
            });
            $.getJSON("geo_layers/classification_74005-US-2016_nonurban.geojson",function(data){
                  L.geoJson(data, {
                      style: miranonurbanstyle
                  }).addTo(mapmirabelurban);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (mapmirabelurban) {
                  var div = L.DomUtil.create('div', 'info legend');
                  div.innerHTML += '<i class="polygon" style="background: #b7484b"></i><span>Urban</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #ffb947"></i><span>Non-urban</span><br>';
                  return div
            }
            legend.addTo(mapmirabelurban);
     </script>
</div>
