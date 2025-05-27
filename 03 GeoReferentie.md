# Georeferentie in BIM 
 
Het ‘ BIM nulpunt’, ofwel ‘coördinatiepunt’ van een model wordt gerelateerd aan RDNEW (EPSG:28992) of RDNEW+NAP (EPSG:7415). Beide zijn geldige geodetische coördinatensystemen. Het coördinatiepunt ligt bij voorkeur zuidwestelijk buiten het 3D bouwwerk binnen de perceelgrens. Op die manier bestaat het lokale assenstelsel uit positieve X- en Y-waarden. De Z-waarde is de waarde ten opzichte van N.A.P. Het begrip ‘Nulpunt’ kan verwarrend zijn omdat het meerdere betekeninssen kan hebben. Het is óf de oorsprong van het absolute nulpunt van de BIM software, óf het is een referentiepunt waarmee geëxporteerd is, óf de referentiekubus in het model óf de oorsprong van het RD-stelsel. Meer hierover vind je in DEEL B (gedeelte software).


![image](https://github.com/user-attachments/assets/5df61c57-8442-4d95-99dd-5b9ee5b5b6f5)

## IFC4

Vanaf IFC4 bestaat de mogelijkheid om IFC-modellen te georefereren; dat wil zeggen niet alleen voorzien van de juiste coördinaten en hoekverdraaiing maar ook de referentie naar het gebruikte coördinatenstelsel is opgenomen in de IFC. De referentie naar het coördinatenstelsel staat in IfcProjectedCRS (EPSG:28992) en de coördinaten worden verwerkt in IfcMapconversion (X=90770. 0000, Y=435320.000, Z=0.400). NB: de waarden ver achter de komma zijn afrondingsverschillen tussen de modelleersoftware en IFC. De hoekverdraaiing Project North > True North staat in XAxisAbscissa (1.) en XAxisOrdinate (6.123233995736766E-017)

![image](https://github.com/user-attachments/assets/00012d84-121d-4203-9bdd-b833d973fc9c)

**Projected CRS name** - De naam van het coördinatenstelsel (EPSG:29882 of EPSG:7415)<br /> 
**Eastings** - De translatie in X-richting tussen de 2 coördinatensystemen (meter)<br />
**Northings** - De translatie in Y-richting tussen de 2 coördinatensystemen (meter)<br />
**Orthogonalheights** - De translatie in Z-richting tussen de 2 coördinatensystemen (meter)<br />
**XAxisAbscissa** - De X-component van de rotatie tussen de twee coördinaten systemen<br />
**XAxisOrdinate** - De Y-component van de rotatie tussen de twee coördinaten systemen<br />
**Scale** - De verschaling tussen de twee coördinatensystemen (b.v. van mm naar m)<br />

Naast IfcProjectedCRS en IfcMapconversion worden ook locatiegegevens opgeslagen in IfcSite. Indien naast IfcSite ook IfcProjectedCRS en IfcMapconversion is verwerkt dan dient IfcSite genegeerd te worden volgens Building Smart. IfcSite is onnauwkeuriger en is gebaseerd op WGS84. Dit stelsel wordt o.a. gebruikt voor GPS en navigatie en werkt met graden-minuten-secondes (Lat: 51,54,13,46643 Lon: 4,27,15,204937), Hoogte (0), LandTitleNumber($), SiteAddress($). LandTitleNumber en SiteAddress zijn vanaf IFC4x3 ADD2 vervallen:

![image](https://github.com/user-attachments/assets/3e5c4532-fb16-4a6b-ae6d-9fe4cd4d41c0)

Dit punt moet dezelfde locatie beschrijven als het punt in IfcMapconversion. Dit kan worden bepaald via de online tool van het Kadaster/NSGI. 

### IFC4 voorbeeld modellen
https://github.com/BILTAcademy/Summit2025/tree/main/LAB5_GEO%20BIM/Resourc
https://github.com/buildingsmart-community/Community-Sample-Test-Files/blob/main/IFC%202.3.0.1%20(IFC%202x3)/SDK%20-%20S1/README.md


## IFC2x3

Het wordt afgeraden IFC2x3 te gebruiken maar het kan zijn dat dit in het BIM-protocol wordt voorgeschreven. Volledig georefereren lukt niet in IFC2x3 (IfcProjectedCRS en IfcMapconversion bestaan niet in IFC2x3) maar coördinaten kunnen wel worden meegegeven aan de Internal Origin:

![image](https://github.com/user-attachments/assets/d10b1174-2d02-4cf3-ba17-49b5db96cf83)

Ook in IFC2x3 bestaat IfcSite en dit werkt hetzelfde als in IFC4x3 ADD2:

![image](https://github.com/user-attachments/assets/66455c26-53f8-4efb-a8e6-97c0f14b5063)

### IFC2x3 voorbeeld model
https://github.com/openBIMstandards/Archive-DataSetSchependomlaan/tree/master/Design%20model%*20IFC




# Georeferentie in GIS 

## CityGML
Translatie geodata. Geen rotatie.

## CityJSON
Translatie geo-data. Geen rotatie.


