# Overdrachtsdocument

In dit document wordt de overdracht van het Urbinn project beschreven. De overdracht bestaat uit het software en documentatie gedeelte van Urbinn.

**Software (Git)**

Alle aangepaste/ontwikkelde software kan gevonden worden op Git ( [https://github.com/urbinn](https://github.com/urbinn)).

**1 URB**

Binnen het onderzoek hebben we een eigen SLAM-algoritme geïmplementeerd. De applicatie, URB ( [https://github.com/urbinn/urb](https://github.com/urbinn/urb)), is voornamelijk gebaseerd op ORB\_SLAM2 ( [https://github.com/urbinn/orb2](https://github.com/urbinn/orb2)) en bevat vooral op het gebied van landmark detection en matching verbeteringen. Deze verbeteringen staan uitvoerig beschreven in het opgeleverde paper.

**2 g2o**

g2o is een graph Optimization library die gebruikt wordt in URB om de motion only bundle adjustment uit te voeren. De bindings met deze library zijn al gemaakt in URB.

**3 BBox-Label-Tool**

Dit is een tool waarmee afbeeldingen gelabeld kunnen worden voor o.a. het object detectie systeem YOLO. Door bounding boxes te tekenen rondom een object en deze te labelen kunnen eigen classificatie verwerkt worden en gebruikt worden om nieuw trainingsmateriaal voor yolo te creëren.

**4 yolo**

Yolo ( [https://pjreddie.com/darknet/yolo/](https://pjreddie.com/darknet/yolo/)) is een systeem die we hebben gebruikt voor object detectie en herkenning. Dit systeem heeft twee varianten waarvan we gebruik hebben gemaakt, namelijk: tiny yolo en yolo9000. Uiteindelijk zijn we verdergegaan met tiny yolo. We hebben tiny yolo ook uitgebreid met een zelf gelabelde dataset. Hiervoor hebben we gebruikgemaakt van de BBox-Label-Tool.

_Overige Urbinn repositories zijn verouderd en hebben geen functie meer in toekomstig onderzoek._

**Documentatie**

Tijdens het onderzoek is er documentatie verzameld, gecreëerd en opgenomen in bijgevoegd .zip file te vinden op git. Deze map bestaat uit:

- **Research papers**
In deze map zijn alle research papers verzameld die gebruikt zijn in het URB project
- **Urbinn paper**

Het paper dat geschreven is naar aanleiding van ons Urbinn onderzoek.

- **Server**

De server hebben we gebruikt voor het opslaan van onze datasets en het testen van  de gemaakte software.

- **Urb FlowChart**

        Er is een flowchart die de stappen van het URB proces afbeelden.

**Tools**

De volgende tools zijn tijdens ons project gebruikt

- **Waffle/issues**

In Waffle hebben wij onze ticket/issues opgenomen, Waffle biedt namelijk de mogelijkheid om de issue aan Git te verbinden.

- **KITTI Evaluation Tool**

Wij hebben de Devkit van Kitti gebruikt om de onze URB runs te evalueren. De devit kan via deze link (http://www.cvlibs.net/datasets/kitti/eval\_odometry.php) gedownload worden.

- **ZED SDK**

We hebben geprobeerd onze eigen opnames te nemen met de ZED Camera van [Stereolabs](https://www.stereolabs.com). Door gebruik te maken van de SDK( [https://www.stereolabs.com/developers/release/2.1/](https://www.stereolabs.com/developers/release/2.1/))  hebben we zelf opnames genomen van een paar gangen in de HHS (Den Haag) en Delft. Deze opnames waren helaas onbruikbaar omdat de software van ORB en URB moeite hadden met de qualiteit van de opnames (alle opnames zijn genomen op fabrieksinstelling). De opnames kunnen gevonden worde op de server onder datasets, slinger…. en delft…. opnames.

De config file voor de camera en een scriptje waarmee je direct png files krijgt uit de camera kunnen hier gevonden worden in de git van Urbinn.

- **Docker**

Docker is virtualisatie software dat veel gebruikt wordt bij de development en deployment van software. Ook wij gebruikten Docker om urb in combinatie met g2o te draaien, zodat er op verschillende platformen ontwikkelt kon worden aan de software.

**Dingen die we zouden willen doen maar geen tijd voor hadden:**
Volledige implementatie van object detection systeem (bv. yolo) in URB. Hierdoor kunnen dynamische en statische object gescheiden worden, met als doel om enkel statische objecten op te nemen in een semantisch map.
