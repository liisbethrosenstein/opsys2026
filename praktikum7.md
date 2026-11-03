# PRAKTIKUM 7
Praktikumis sain esimest korda tegeleda haakimiseg ja uurida, mis see täpsemalt on. 
# 7.1
Uued andmekandjad tuleb lähtestada, sest kettal puudub partitsioonitabel, mida arvuti ära tunneks. Ilma tabelita operatsioonisüsteem ei tuvasta ketta struktuuri ega leia partitsioone. Kui  partitsioonid on loodud, saab igale partitsioonile luua failisüsteemi ja hakata andmeid salvestama,

# 7.2 

1. Kettamaht: MBR toetab ainult kuni 2 TB, aga GPT lubab kuni 9,4 ZB. See on parem, sest saab kasutada tänapäevaseid suuri kettaid ühe tervikliku partitsioonina.

2. Partitsioonide arv: MBR-s saab olla ainult 4 primaarset partitsiooni, GPT-s aga vaikimisi 128. See on parem, sest saab paindlikult hallata mitut OS-i ja eraldatud kaustu ilma keerulise loogiliste partitsioonide süsteemita.

3. Andmete terviklikkus: MBR hoiab tabelit ainult ühes kohas ja kontrollsummat pole, GPT hoiab aga nii primaarset kui ka sekundaarset koopiat koos CRC32 kontrollsummadega. See on parem, sest vigastatud tabel saab automaatselt taastuda ja andmete riknemist on võimalik tuvastada.

4. Buutimine: MBR paneb buutimislaadurile 446-baidise piirangu, GPT toetab aga UEFI-t ja eraldi EFI partitsiooni. See on parem, sest saab kasutada suuremaid buutimislaadureid, Secure Boot'i ja kiiremat käivitumist.

# 7.3 
https://kodu.ut.ee/~rosenstein/opsys/hdd.png

# 7.4 

<img width="978" height="578" alt="Screenshot 2026-11-03 141456" src="https://github.com/user-attachments/assets/4a9b681b-0245-4d76-b13a-d47a7fe15f42" />

# 7.5 
o -ro faili saab ainult lugeda ehk saad avada ja vaadata, aga mitte muuta.

t - auto automaatselt tuvastab mälupulga failisüsteemi tüübi.


# 7.6 
Auto väärtus asendub defaults 'ga

# 7.7
<img width="1464" height="959" alt="Screenshot 2026-11-03 144209" src="https://github.com/user-attachments/assets/fa9b09ea-3930-4495-81a4-77f9534c8983" />
