La caméra OV7675 est un capteur CMOS matrice de millions de petits capteurs de lumière cabler avec notre arduino BLE nano 33 via bus I2C pour configuration depuis arduino de la résolution,format couleur ,luminosité,contraste.
Puis avec les pin D0 D7 chaque valeur de pixel est reçue par la carte arduino aprés qu'un déclenchement d'une capture d'un nouveau image soit faite par VSync et pour chaque nouveau ligne de pixel HREF etat haut puis bas donne le signal d'aquisition puis avec PCLK l'horloge permettant d'envoyer chaque nouveau données de pixels.
Ainsi la bibliothéque ov7576 est utilisé pour l'acquisition des images de résolution 160x120 qui sont redimensionner puis passer sur le modéle générer par edge impulse qui fait la prediction.
En effet edge impulse génére la bibliothèque <classification_component_inferencing.h> contenant le modèle IA et la fonction run_classifier qui permet de faire la prediction sur l'image acquis avec le ov7576 à l'aide de 3 paramétre:
Une entrée de données pour les valeur des pixel &signal ,&result la valeur prédite et debug_nn pour des besoin debug des valeurs intermédiaire envoyé par le modéle.
Une fois l'image prédite elle est envoyé via le port série vers node-red où un dashbord permet d'incrémenter chaque valeur de composant prédite (voir vidéo inférence ) le modéle parvient à predire correctement les composant mais de maniere trés limité avec la taille de notre dataset faible nous avons un modéle ayant sur appris qui s'est trop généraliser sur les données comme le montre notre matrice de confusion <img width="1085" height="665" alt="image" src="https://github.com/user-attachments/assets/674b6f83-4c72-4a3c-ba29-2fca4979456c" /> où le modéle à parvenu à predire les composant correspondant aux  image réel de chaque label avec un trés faible loss. Ceci fait donc notre modéle bien qu'il soit capable de préidire correctement chaque composant elle trés limité et sensible au bruit.







