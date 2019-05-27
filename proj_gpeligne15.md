---
title: Grand Paris Express
layout: default
---
# The Grand Paris Express around Paris, Line 15
Small project that draws the intended ligne around the city of Paris.
<div id="mapid" style="width: 600px; height: 400px">
      <script>
            var map = L.map('mapid').setView([48.854908, 2.367671], 11);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
                  attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
                  maxZoom: 18,
                  id: 'mapbox.streets',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(map)
            $.getJSON("ligne15_ligne.geojson",function(data){
                  L.geoJson(data).addTo(map);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (map) {
                  var div = L.DomUtil.create('div', 'info legend');
                  labels = ['<strong>Metro</strong>'],
                  categories = ['Line 5'];
                  div.innerHTML = labels.join('<br>');
                  return div
            }
            legend.addTo(map);
     </script>
</div>
[Homepage](./index.html)
