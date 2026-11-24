# Praktikum 10
Praktikumis tutvusin erinevate tööriistadega Windowsis kui ka Linuxis,peamiselt kust leida infot erinevate asjade kohta. Sain katsetada, mida erinevad tööriistad teevad ja kuidas õige info kätte saada.



| Küsimus | Linux | Windows | Linuxis kasutatud käsklus | Windowsis kasutatud tööriist ja väli |
|---|---|---|---|---|
| Ülesanne 10-1 (Protsesside arv) | 281 | 135 | `ps aux \| wc -l` | Task manager -> performance -> CPU |
| Ülesanne 10-2 (Esimene protsess) | usr/lib/systemd/ | smss.exe | `ps axo pid,cmd,comm,etime \| head` | Process explorer -> view -> columns -> start time |
| Ülesanne 10-3 (Töötavad protsessid) | avahi, _chrony, colord, cups-browsed, liisbeth, messagebus, polkitd, root, rtkit, syslog, systemd-oom, systemd-resolve, USER | NT AUTHORITY\SYSTEM, ROSENSTEIN-W11\Liisbeth, NT AUTHORITY\LOCAL SERVICE, Window Manager\DWM-2, Font Driver Host\UMFD-0, Font Driver Host\UMFD-2, NT AUTHORITY\NETWORK SERVICE | `ps -eo user \| sort -u` | Process explorer -> view -> columns -> user name |
| Ülesanne 10-4 (Töötamise aeg) | 24 minutit | 45 minutit | `uptime -p` | Task manager -> CPU -> uptime |
| Ülesanne 10-5 (Viimane protsess) | kworker/u19:0 | smartscreen.exe | `ps axo pid,cmd,comm,etime --sort=+etimes \| tail -n +5 \| head` | Process explorer -> start time |
| Ülesanne 10-6 (Protsessori aeg) | /usr/bin/gnome-shell --mode 5% | system 2.6% | `ps axo pid,cmd,comm,pcpu --sort=-pcpu \| head` | Task manager -> processes |
| Ülesanne 10-7 (Virtuaalmälu) | /usr/bin/gnome-shell --mode | msedgewebview2.exe (6360) | `ps axo pid,cmd,comm,vsz --sort=-vsz \| head` | Process explorer -> columns -> process memory -> virtual size |
| Ülesanne 10-8 (Füüsiline mälu) | /usr/bin/gnome-shell --mode | explorer.exe | `ps axo pid,cmd,comm,sz --sort=-sz \| head` | Process explorer -> working set column |
| Ülesanne 10-9 (Füüsilise mälu kasutus) | Hõivatud (used) 1724 MB / 1.68 GB / 50.8 %; Vaba (available) 1671 MB / 1.63 GB / 49.2 % | 2.3 GB (1741 MB) (57%) on kasutuses, 1.7 GB (2355 MB) (43%) on vaba | `free -m` ja `free -h` | Task manager -> CPU |
| Ülesanne 10-10 (Põhiketta vabaruum) | 8.0G (34% free) | 31.8 GB, 50.6% vaba | `df -h / \| awk 'NR==2 {print "Free Space: " $4 " (" 100 - $5 "% free)"}'` | File explorer -> Local disk C -> Properties |
| Ülesanne 10-11 (Suurim fail & kaust) | Fail: /swap.img; kaust: /usr | Suurim fail: pagefile.sys; suurim kaust: Windows | `sudo find / -xdev -type f -printf '%s %p\n' 2>/dev/null \| sort -nr \| head -n 5` ja `sudo du -h -x -d 1 / 2>/dev/null \| sort -hr \| head -n 8` | WinDirStat |
| Ülesanne 10-12 (Terminali käsud Linux) | /dev/zero: us ja sy võrdselt 40.4 %; /dev/urandom: sy 5.6 % > us 4.9 % | puudub | `top` ja `sha1sum /dev/urandom \| sha1sum /dev/urandom`; `top` ja `sha1sum /dev/zero \| sha1sum /dev/zero` | puudub |
| Ülesanne 10-12 pildid | <img width="1469" height="1020" alt="Screenshot 2026-11-24 133737" src="https://github.com/user-attachments/assets/86c4f4e3-2eb1-49bd-9c1a-0e24f0e2b274" /> | <img width="1661" height="873" alt="Screenshot 2026-11-24 140026" src="https://github.com/user-attachments/assets/0efbb5e7-3b3e-4460-896b-14818fc42486" /> | | |
| Ülesanne 10-13-1: Milline protsess kirjutab kõige rohkem salvestusseadmele? | puudub | system | puudub | Resource Monitor -> Disk |
| Ülesanne 10-13-2: Millisesse faili eelmise küsimuse protsess kõige rohkem kirjutab? | puudub | C:\$LogFile | puudub | Resource Monitor -> Disk |
| Ülesanne 10-13-3: Milline protsess loeb kõige rohkem salvestusseadmelt? | puudub | MsMpEng.exe | puudub | Resource Monitor -> Disk |
| Ülesanne 10-13-4: Millisest failist eelmise küsimuse protsess kõige rohkem loeb? | puudub | C:\ProgramData\Microsoft\Windows Defender\Scans\mpcache-39523C4746E35A5F60FBB0FDDA33C43DD15AB747.bin.67 | puudub | Resource Monitor -> Disk |
| Ülesanne 10-14 (Võrguliiklus) | puudub | nextcloud.exe (PID 2664); 10.0.2.15:51487 -> 193.40.5.90:443 (owncloud.ut.ee); latentsus 1 ms; liiklus 207 B/sec (Send 84, Receive 122) | puudub | Resource Monitor -> Network -> TCP Connections (aadressid, pordid, latentsus) ja Network Activity (Total B/sec) |
| 10.14 pilt | <img width="1904" height="1123" alt="10 14" src="https://github.com/user-attachments/assets/8eb9ebbe-fab2-48a7-84ca-4fe9ea086776" /> | | | |
| Ülesanne 10-15 | Valisin Linuxi | | 1. `uptime` ja `nproc`: load average peab olema väiksem kui tuumade arv. Püsivalt suurem tähendab ülekoormust. 2. `top`: vaatan rida %Cpu(s). us > 80–90 %: mõni programm koormab protsessorit. wa > 10–20 %: protsessor ootab ketast. st > 5 % (VM-is): hüperviisor võtab CPU-d. Sorteerin veeru %CPU (klahv P) ja %MEM (klahv M) järgi ning otsin protsessi, mis on püsivalt üle 80–90 % CPU-d või mitu GB mälu. 3. `free -h`: veerg available alla 10 % kogumahust või suur Swap used tähendab mälupuudust. 4. `vmstat 1 10`: si / so püsivalt > 0: saalimine. wa > 10–20 %: kettaprobleem. r > tuumade arv: CPU ülekoormus. 5. `df -h` ja `df -i`: Use% ja IUse% > 90 % tähendab täis ketast. Põhjuse leian käsuga `sudo du -h -x -d 1 / \| sort -hr \| head -n 8`. 6. `ps -eo pcpu,pmem,pid,user,args --sort=-pcpu \| head -n 10`: annab 10 suurimat CPU-kasutajat. | |
