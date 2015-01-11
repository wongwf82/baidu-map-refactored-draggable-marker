# baidu-map-refactored-draggable-marker
Refactored Baidu Map implementation with search box autocomplete. Map is in a Bootstrap modal and pops up when user navigates away from address text field. Markers can be moved by dragging or clicking another point in the map. 

A few things to note:

1. The implementation was in Ruby on Rails. Feel free to extract what you need (esp. the Javascript portion).

2. The flow is:<br>
(a) User moves navigates away from address text field<br>
(b) The modal pops up<br>
(c) User enters a location to be searched<br>
(d) User can click/drag marker<br>
(e) User clicks Done button<br>
(f) The city field gets updated<br>
(g) The next field (Phone) is highlighted 
