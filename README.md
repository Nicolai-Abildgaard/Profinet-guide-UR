# Profinet-guide-UR
Profinet connection between UR3e and Siemens S71500

Guide til profinet forbindelse mellem UR3e og S71500. 

1) Link til guide - https://www.universal-robots.com/articles/ur/interface-communication/profinet-how-to-guide-e-series/ 

2) Start med at downloade den tilhørende GSDML fil., og UR.DataStruct.

3) Find robotten ved at finde den i kataloget til højre, "Other devices", "IO Devices" "UR" ca. også træk den ind.

4) Lav en PN/IE forbindelse mellem plc og den indsatte UR enhed.

5) Search netværket for tilhængelige enheder, tildel ur enheden en ip og subnet, samt et tilhørende navn.

6) Tryk på det indsatte UR enhed og her skal den netop angivne ip adresse og device name skrives ind.

7) I projekttræet vælges External source files, og her hentes UR.DataStruct filen. 

8) Højreklik på filen, og tryk på opret tilhørende blokke.

9) Åben PLC tags, og opret følgende to tags - UR-T20 & UR-02T.
