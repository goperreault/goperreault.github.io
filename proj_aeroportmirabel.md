---
title: Mirabel Airport
layout: default
---

# Mirabel Airport Land Coverage
A project that shows the coverage of the Mirabel Airport.

## Land
Map that shows the required land that was expropriated for the construction of the airport.
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
Map that shows how the land is used based on 2016 data. According to the [city's website](https://ville.mirabel.qc.ca/ville/a-propos-de-mirabel), Mirabel is home to 55 020 residents, where 87% of the land being for agricultural uses.
<div id="mapidmirabelclass" style="width: 700px; height: 500px">
      <script>
            var mapmirabelclass = L.map('mapidmirabelclass').setView([45.657400, -74.075657], 10);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: '<a href="https://www.tvanouvelles.ca/2015/10/06/des-images-de-laeroport-rarement-vues">TVA Nouvelles/Des images de laéroport rarement vues</a><br>Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
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
                    fillColor: "#18b8a8",
                    weight: 2,
                    opacity: 0.5,
                    color: "#18b8a8",
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
                    fillColor: "#feb401",
                    weight: 2,
                    opacity: 0.5,
                    color: "#feb401",
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
                    fillColor: "#a90f32",
                    weight: 2,
                    opacity: 0.5,
                    color: "#a90f32",
                    fillOpacity: 0.5
                  }
                  case 'Rue ou ruelle': return {
                    fillColor: "#a90f32",
                    weight: 2,
                    opacity: 0.5,
                    color: "#a90f32",
                    fillOpacity: 0.5
                  }
                  case 'Stationnement': return {
                    fillColor: "#a90f32",
                    weight: 2,
                    opacity: 0.5,
                    color: "#a90f32",
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
                    fillColor: "#a9a9b8",
                    weight: 2,
                    opacity: 0.5,
                    color: "#a9a9b8",
                    fillOpacity: 0.5
                  }
                  case 'Zone ferroviaire': return {
                    fillColor: "#9999a6",
                    weight: 2,
                    opacity: 0.5,
                    color: "#9999a6",
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
                  var div = L.DomUtil.create('div', 'info legend');/*,
                  labels = ['<strong>Metro</strong>'],
                  categories = ['Line 5'];
                  labels.push(categories);
                  div.innerHTML = labels.join('<br>'); */
                  /*div.innerHTML += "<h4>Metro</h4>";*/
                  div.innerHTML += '<i class="polygon" style="background: #a90f32"></i><span>Mirabel Landuse</span><br>';
                  return div
            }
            legend.addTo(mapmirabelclass);
     </script>
</div>
