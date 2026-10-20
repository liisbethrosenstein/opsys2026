# Praktikum 5
Praktikumis õppisin Linuxi protsesse vaatama, käivitama taustal ning peatama ja lõpetama. Harjutasin signaalide kasutamist ja protsesside sisendi ning väljundi suunamist failidesse. Samuti tutvusin zombiprotsesside ja nohup-käsuga.
Lisan om töö tõestused. 

# 5.1
<img width="1315" height="1028" alt="5 1 2" src="https://github.com/user-attachments/assets/4e5f7e0c-a33f-469e-b8f2-898e310cdb6f" />
<img width="1324" height="1022" alt="5 1 1" src="https://github.com/user-attachments/assets/4b8bf13f-f8d0-4a80-9a01-6b3fa36afa0a" />

# 5.2

<img width="1726" height="1092" alt="Screenshot 2026-10-20 171143" src="https://github.com/user-attachments/assets/e3709ddb-3d10-4ba2-81f9-6f3ea5a00f2f" />




# 5.3
ps -axu | grep daemon | grep -v grep | tr -s ' ' | cut -d' ' -f11- | grep daemon
<img width="1407" height="1010" alt="Screenshot 2026-10-20 161621" src="https://github.com/user-attachments/assets/0c716144-0b2f-4117-8622-6216c1870eda" />

# 5.4
ip a | grep 'inet ' | grep 'scope global' | tr -s ' ' | cut -d' ' -f3 | cut -d'/' -f1 > ipaddress.txt
<img width="1400" height="1003" alt="Screenshot 2026-10-20 162411" src="https://github.com/user-attachments/assets/cb30d5bb-4e11-4e23-ad67-da2f709087ab" />

# 5.5
16:39:10.458,512,"WM_MOUSEMOVE",0,12714501
See näitab seda, et üksi klahv ei olnud all hiire liikumise ajal(https://learn.microsoft.com/en-us/windows/win32/inputdev/wm-mousemove)

16:39:10.421,48,"WM_SETFONT",722080018,1
Määrab fondi, mida juhtelement teksti kuvamisel kasutab. 
(https://learn.microsoft.com/en-us/windows/win32/winmsg/wm-setfont)
