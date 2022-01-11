# MongoDB

Lorsqu'on souhaite retrouver des éléments dans un contexte géospatial, on peut utiliser des requêtes géospatiales. Celles-ci servent à sortir toutes les données d'une base de données qui peuvent être proches d'un point donné sur une carte, un polygone, etc...
Ainsi, on peut savoir quels sont par exemple les magasins les plus proches de notre location, ou d'un autre lieu en particulier, ou encore les cinémas.
On utilise donc des requêtes pour les données GeoJson, qui tournent à partir des mots-clés $near et $within. On utilise le premier pour déterminer les données proches d'un point précis, et le second pour déterminer toutes les données présentes dans une zone donnée.

