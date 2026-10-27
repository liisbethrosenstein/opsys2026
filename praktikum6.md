# Praks 6

# 6.1
a) Kataloogil peab olema kävitamise õigus (x) ja failil lugemise õigus (r)

b) Kataloogil peab olema käivatamise õigus (x) ja kirjutamise õigus (w). Failil ei ole vaja õiguseid. 

# 6.2 
Käsu käivatmaisek ei ole käsk,  chmod a=x skriptifail, piisav, sest on vaja ka lugemisõigust (r). Kui lugemis õigus puudub ei saa faili sisu kätte.

# 6.3 
Linux loob igale kasutajale eraldi privaatgrupi, et vaikimisi `umask 0002` saaks anda grupile kirjutamisõiguse, ilma et teised kasutajad saaksid failie juurdepääs. Turvalisuse tagab kohselt see, et ainult omanik saab faile muuta. Kui on vaja faile jagada, piisab lihtsalt teiste kasutajate lisamisest samasse gruppi, mis annab neile vajalikud õigused.

# 6.4 

<img width="1109" height="800" alt="image" src="https://github.com/user-attachments/assets/2455a42c-a024-4519-9b4c-f1875cca9451" />

# 6.5 

<img width="1102" height="833" alt="image" src="https://github.com/user-attachments/assets/f9ebd09e-242d-4e92-ae8a-0b2738034607" />
setuid-õigust on vaja selleks, et anda tavakasutajale programmi käivitamise ajaks programmi omaniku õigused

# 6.6 
Setuid on väga mugav viis anda ajutiselt  tavakasutajale kõrgemaid õigusi ilma, et peaks talle andma root õigusi
Kui programm on halvasti tehtud, saab igaüks seda ära kasutada. Nii võib tavakasutaja saada endale admini õigused ja pääseda ligi failidele, kuhu muidu ei saaks.  

# 6.7
Peetri failie saavad ligi Peeter ise, opetaja ja root kasutajad.

# 6.8

Õiguste rea lõppu oli tekinud + märk. 
# file: hinded.txt
# owner: opetaja
# group: opetaja
user::rw-
group::---
group:direktor:rw-
mask::rw-
other::---

