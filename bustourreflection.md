---
title: Bus Tour Reflection
layout: layoutTMU
---
## Bus Tour Reflection
A project identifying diversity and inclusivity during a bus tour of the Mississauga Chinese Centre and The Great Punjab Business Centre, located in Mississauga, Ontario, Canada.

**Site Map**
<div id="mapidbustour" style="width: 700px; height: 500px">
      <script>
            var mapbustour = L.map('mapidbustour').setView([43.64148815020137,-79.61874431494705], 11);
            L.tileLayer('https://api.mapbox.com/styles/v1/{id}/tiles/{z}/{x}/{y}?access_token={accessToken}', {
                  attribution: '© <a href="https://www.mapbox.com/about/maps/">Mapbox</a> © <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a> <strong><a href="https://www.mapbox.com/map-feedback/" target="_blank">Improve this map</a></strong>',
                  maxZoom: 18,
                  id: 'mapbox/streets-v11',
                  accessToken: 'pk.eyJ1IjoiZ3BlcnJlYXVsdDkxIiwiYSI6ImNqdXJqYmxubTBpbDU0M25wdm5hMnk2dGEifQ.xS5T9S5SvQKL8wiChwUErA'
            }).addTo(mapbustour)
            L.marker([43.59789523871053,-79.59447134236618]).addTo(mapbustour)
            .bindPopup('Mississauga Chinese Centre')
            .openPopup();
            L.marker([43.7095005796771,-79.65271204349811]).addTo(mapbustour)
            .bindPopup('The Great Punjab Business Centre');
          function punjabstyle(feature) {
                return {
                  fillColor: "#ffb947",
                  weight: 2,
                  opacity: 0.5,
                  color: "#ffb947",
                  fillOpacity: 0.5
                };
            }
            function chinesestyle(feature) {
                return {
                  fillColor: "#b7484b",
                  weight: 2,
                  opacity: 0.5,
                  color: "#b7484b",
                  fillOpacity: 0.5
                };
            }
            function censusstyle(feature) {
                return {
                  fillColor: "#194a8d",
                  weight: 2,
                  opacity: 0.5,
                  color: "#194a8d",
                  fillOpacity: 0.1
                };
            }
            $.getJSON("geo_layers/MissChineseBusi.geojson",function(data){
                  L.geoJson(data, {
                      style: chinesestyle
                  }).addTo(mapbustour);
            });
            $.getJSON("geo_layers/GreatPunjabBusi.geojson",function(data){
                  L.geoJson(data, {
                      style: punjabstyle
                  }).addTo(mapbustour);
            });
            $.getJSON("geo_layers/ct_5350510.geojson",function(data){
                  L.geoJson(data, {
                      style: censusstyle
                  }).addTo(mapbustour);
            });
            $.getJSON("geo_layers/ct_5350528.geojson",function(data){
                  L.geoJson(data, {
                      style: censusstyle
                  }).addTo(mapbustour);
            });
            var legend = L.control({position: 'bottomleft'});
            legend.onAdd = function (mapbustour) {
                  var div = L.DomUtil.create('div', 'info legend');
                  div.innerHTML += '<i class="polygon" style="background: #b7484b"></i><span>Mississauga Chinese Centre</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #ffb947"></i><span>The Great Punjab Business Centre</span><br>';
                  div.innerHTML += '<i class="polygon" style="background: #194a8d"></i><span>Census Tract</span><br>';
                  return div
            }
            legend.addTo(mapbustour);
     </script>
</div>


**Background Demographics**

The City of Mississauga has a highly diverse population of Chinese and Punjab residents. In fact, 7.8% of the total population denotes their ethnic/cultural origin as Chinese, while 1.5% denotes their ethnic/cultural origin as Punjabi. At the local level, the census tract for the Mississauga Chinese Centre denotes 3.7% of the population as Chinese ethnic/cultural origin. For The Great Punjab Business Centre, 4.3% of the population denotes their ethnic/cultural origin as Punjabi. These numbers showcase the different ethnic and cultural origins as being important to the cultural make up of the city.

**Site Description**

The Mississauga Chinese Centre stands out as a landmark along Dundas Street. Its entryway gives the impression of a specifically Asian centre. The entry into the centre displayed the types of uses, including mostly retail spaces. The arch also serves as a break into the existing landscape along Dundas Street, which is populated by other retail spaces and a residential neighbourhood. The large residential slab across the street reflects this break, which ironically, the centre’s towers meant to imitate a view over the city, gets overshadowed by this slab. In contrast, the mostly empty lands adjacent to the slab shows potential for further development around the site. In addition, the train tracks, which carry Go Transit’s Milton Line, delineate the site and the neighbourhood’s activities to Dundas Street.
In contrast, The Great Punjab Business Centre blends with its surroundings along the Airport Road industrial corridor. The entryway, located on Drew, offers a familiar built form to any commercial and retail spaces. It is only once visitors enter the site that the intricate details of the buildings become more prominent. The colour and choice of material exemplifies the centre as a retail and commercial space for the Punjab community.


**Key Features of the Site**

According to the numerous inscriptions along the site, the centre was built to imitate a Chinese commercial centre and city, with its large corner towers, the arch, the nine dragon wall, Soo Chow garden, the fortress, the stele, and the covered walkways. Indeed, these walkways are meant to “imitate the ones in Beijing”, which offers protection and serves as a marker for the retail spaces along the site. Culturally, the nine dragon wall, defined as the only one outside of Asia, reinforce the space’s clear Chinese influence and offers a strong welcoming marker for customers entering the space. In fact, one may not call them customers, but merely citizens of the space, as the site offers a home away from home, even if they have always lived in Canada. The large tower of the fortress serves as a second marker for those who enter the space by its second entrance, further implying the space’s purpose as a Chinese centre.
The Punjab business centre offers a few landmarks to denote the space for its community. First, the mural wall with the engraved history denotes the site’s focus on the Punjab community. As written, the depiction of the Komagata Maru gives way for reflection as to how these immigrants arrived in Canada. Next, the statue of Maharaja Ranjit Singh depicts the founder of the Sikh Empire overlooking and acting as overlooker on the site. The Sikh Heritage Museum of Canada located amongst the retail spaces and offices, further entrenches the cultural usage of the site. As such, businesses and offices offer diverse services to the community, including integration services offering immigrants an opportunity for life in Canada.


**Inclusive Spaces**

Inclusivity, which aims to remove barriers for all, defines the overall character of the space. The retail spaces offer services to all customers. The plaques located around the centre that define its built form also includes English for those who wish to better understand the space’s character.
The Punjab business centre’s many job centre offering establishes an inclusive environment to integrate the community’s needs with the surrounding reality of Canadian life. Located amongst industrial spaces around the airport, and close to the strong Sikh population in Brampton, confirms the choice of this location as close to its community.


**Knowledge and Sharing**

To learn and share knowledge about another culture is important for planners. As we aim to build inclusive communities, knowledge serves as a guide to better understand the goal and purpose of these spaces. As such, the centre’s use of descriptive imagery in the fortress’ hallway helps outsiders to appreciate the built form and purpose of the centre as central to the Chinese community. The mix of guidance and retail offers a theoretical and practice use of the space, where one may wish to immerse themselves and discover a foreign cultural community. In similar fashion, the landmarks around the Punjab business centre reinforce the notion of the space as welcoming to the Sikh and non-Sikh community. The inclusion of the museum further demonstrates the space as knowledge sharing within the larger communities in the Greater Toronto Area.


**How to approach a space as a planner and gain knowledge**

A strong background about the space before visiting would be encouraged to better prepare ourselves. This can be achieved through simply researching about the existing community and its historical immigration to the country. In addition to the offerings of knowledge each space may have, planners should be concerned with the history of the space, such as the choice of location, existing surroundings, and how it was planned to interact with established communities.
Planners should learn about the history of the site, including why this space was chosen to locate the Chinese centre. As such, a careful study of zoning by-laws and demographics of the city can aid in offering a better understanding of the site. Information may also be contained in research conducted about the community. Epistemological studies about the community offers a dialogue between researchers and the people of the community. Future goals and purposes by the city can inform possible changes and impacts to the space, for example the Dundas Connects which can aim to offer an alternative to the automobile for travelling to the site.

## Mississauga Chinese Centre
![arch](./tourpics/arch.jpg)
![coveredwalkway](./tourpics/coveredwalkway.jpg)
![ninedragonwall](./tourpics/ninedragonwall.jpg)
![pavilion](./tourpics/pavilion.jpg)

## The Great Punjab Business Centre
![muralentrance](./tourpics/muralentrance.jpg)
![muralwall](./tourpics/muralwall.jpg)
![statue1](./tourpics/statue1.jpg)
![statue2](./tourpics/statue2.jpg)
![sikhmuseum](./tourpics/sikhmuseum.jpg)
![gurdwara](./tourpics/gurdwara.jpg)
