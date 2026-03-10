Pour faire ce projet edge impulse nous avons connecter la carte arduino nano 33 puis sur data acquisition construire le dataset <img width="2859" height="1156" alt="image" src="https://github.com/user-attachments/assets/d0f805f5-791d-4bea-bbf4-785f10816719" />
Le dataset a directement été construit avec le capteur OV7576 pour 3 label potentiométre , Led ,resitance.
Pour chaque Label, nous avions fait une trentaine d'acquisition puis spliter en train et test pour 80%/20%.
Ensuite choisir le modéle classifier et définir la taille des images 28x28 sur create impulse puis sur image choisir grayscale puis entrainer le modèle sur classifier  faire le teste sur Model testing et déployer le tout sur deployement en choisissant arduino library.


