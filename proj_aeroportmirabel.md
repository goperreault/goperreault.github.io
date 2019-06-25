---
title: Mirabel Airport
layout: default
---

# Mirabel Airport Land Coverage
A project that shows the coverage of the Mirabel Airport.

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
