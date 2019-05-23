---
layout: default
---

## Welcome to my website!
Showcasing geography related projects.

## Ash trees in Mississauga
![Branching](./Ash_trees.jpeg)

## Leaflet map
<div id="mapid" style="width: 600px; height: 400px">
      <script>
            var mymap = L.map('mapid').setView([43.588, -79.648], 11);
            L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
            attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
            maxZoom: 18,
            id: 'mapbox.streets',
            accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(mymap);
            $.getJSON("Tree_3857_ash.geojson",function(data){
            L.geoJson(data).addTo(map);
            });
            
            
     </script>
</div>

[About me](./about.html)
