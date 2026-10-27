# Praks 6

# 6.1
a) Kataloogil peab olema käivitamise õigus (x) ja failil lugemisõigus (r)

b) Kataloogil peab olema käivitamise õigus (x) ja kirjutamise õigus (w). Failil pole vaja õigusi.

# 6.2 
Käsu käivatma ei ole käsk,  chmod a=x skriptifailile piisav, sest on vaja ka lugemisõigust (r). Kui lugemisõigus puudub, saa faili sisu kätte.

# 6.3 
Linux loob igale kasutajale eraldi privaatgrupi, et vaikimisi `umask 0002` võimaldaks anda grupile kirjutamisõiguse, ilma et teised kasutajad saaksid failidele juurdepääsu. Turvalisuse tagab kohselt see, et ainult omanik saab faile muuta. Failide jagamiseks, piisab lihtsalt teiste kasutajate lisamisest samasse gruppi, mis annab neile vajalikud õigused.

# 6.4 

<img width="1109" height="800" alt="image" src="https://github.com/user-attachments/assets/2455a42c-a024-4519-9b4c-f1875cca9451" />

# 6.5 

<img width="1102" height="833" alt="image" src="https://github.com/user-attachments/assets/f9ebd09e-242d-4e92-ae8a-0b2738034607" />
setuid-õigust on vaja selleks, et anda tavakasutajale programmi käivitamise ajaks programmi omaniku õigused

# 6.6 

Setuid on turvalisem kui tavakasutajale root õiguste andmine, kuid see suurendab süsteemi ründamise võimalusi. Setuid laseb tavakasutajal käivitada programmi ilma root õigusteta. See tekitab riske kui programm on viga ja seda saab rünnata, et õigused enda kätte võtta.

# 6.7
Peetri failie pääsevad ligi Peeter ise, opetaja ja root kasutajad.

# 6.8

Õiguste rea lõppu oli tekinud + märk, mis näitab, et failil on ACL.
#file: hinded.txt
#owner: opetaja
#group: opetaja
user::rw-
group::---
group:direktor:rw-
mask::rw-
other::---

# 6.9
Mitte keegi ei saa sellise faili sisu muuta

Kõige pealt tuleb eemaldada failit atribuut +i: sudo chattr -i testfail-2

Siis kustutame faili: rm testfail-2

