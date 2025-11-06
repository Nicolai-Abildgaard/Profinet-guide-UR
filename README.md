# Profinet-guide-UR

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

10) Compile og download, dette skulle gerne resultere i grønne flueben, og at man kan se UR robottens værdier i PLC tags.

11) Lav nu følgende tags <img width="1715" height="1080" alt="Tag1" src="https://github.com/user-attachments/assets/7c29ddd2-15f4-47d1-a7cb-2256fa670128" />


12) For at finde tcp koordinaterne skal man have følgende adresser:
TCP_1.X= %ID215
TCP_1.Y = %ID219
TCP_1.Z = %ID223

Disse skal så konverteres.


12) Følgende kode bruges til at konvertere fra DWORD som UR sender til REAL.
    <img width="1920" height="1028" alt="Main" src="https://github.com/user-attachments/assets/978cdccf-d610-40ea-a359-50569ce123a1" />

"UR_X" := DWORD_TO_REAL(SWAP_WORD(SWAP_DWORD( "UR_Raw_X")));
"UR_Y" := DWORD_TO_REAL(SWAP_WORD(SWAP_DWORD( "UR_Raw_Y")));
"UR_Z":= DWORD_TO_REAL(SWAP_WORD(SWAP_DWORD( "UR_Raw_Z")));

"UR_X_mm" := "TCP_1.X" * 1000.0;
"UR_Y_mm" := "TCP_1.Y" * 1000.0;
"UR_Z_mm" := "TCP_1.Z" * 1000.0;
