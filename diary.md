## [2026-06-21] – Cross-compiler elkészítése
## Cross-compiler helye a saját fájlstruktúrámban: /mnt/build/opt/cross/bin/i686-elf-gcc
## Cross-compiler elérése egyszerűen: A $crossgcc környezeti változó az i686-elf-gcc fájlra mutat 


### Mit csináltam
- Megcsináltam a cross-compilert amivel az új operációs rendszerre fogok programokat fordítani

### Miért
- Szükség van egy új cross-compilerre, egy olyanra ami nem használ semmilyen windowsos/linuxos könyvtárat vagy fejlécet mert ezeket egy teljesen új operációs rendszeren nem tudnánk futtatni.

### Problémák / hibák
- Az OSDEV wikin fellelhető anyagok leginkább linuxra vannak specializálva. Az én gépemen alapvetően windows van ezért be kellett üzemelnem egy virtuális gépet.
- Nem mindegy, hogy milyen gcc-t és linkert használunk a cross-compiler elkészítéséhez. Az én virtuális gépemen kissé elavult volt mindkettő, ezért először be kellett szereznem egy viszonylag új linkert és gcc-t.
Linkerből 2.45-ös verziót használtam, gcc-ből 15.2.0-s verziót. 
- Azt hittem, hogy mindenképp kell készíteni egy külön compilert amivel majd a cross-compilert készítjük. Kiderült, hogy ez csak akkor kell ha elavult a gcc-d, így ez teljesen felesleges lépés volt és nagyon sok időm elment vele.
- Az új cross-compiler buildelésekor elfogyott a tárhely a virtuális gépen ezért adnom kellett több tárhelyet.

### Megoldás / tanulság
- Figyelmesen elolvasni mit írnak az OSDEV oldalon és akkor nem futok bele felesleges lépésekbe.
- Legyen mindig elegendő tárhely a virtuális gépen és legyen elegendő erőforrás (RAM, CPU) adva neki.

### Következő lépés
- Hozzáadtam a PATH-hoz az új cross-compilert, hogy el tudjam érni könnyen amikor szükség lesz rá


## [2026-06-26] – OSDEV wiki basic introduction rész elolvasása, barebones tutorial elkezdése

### Mit csináltam
- Először is elolvastam az OSDEV wiki basic introduction szekciójában található oldalakat
- Aztán leellenőriztem, hogy még mindig megvan-e a cross-compiler amit a múltkor csináltam
- Elkezdtem az OSDEV wiki barebones tutorialját: GRUB bootloadert használva írunk egy alap kernelt

### Miért
- Elolvastam az OSDEV wiki basic introduction szekciójában található oldalakat, hogy képben legyek, hogy mire számítsak a továbbiakban
- Biztosra akartam menni, hogy nem törlődött a virtuális gépről semmi csak úgy
- A barebones tutorial az oldalon egy kezdőknek készült tutorial, úgy gondoltam érdemes azzal kezdeni

### Problémák / hibák
- Amikor le akartam ellenőrizni, hogy megvan-e még a cross compiler amit a múltkor csináltam akkor azt láttam, hogy nincsen. Ez azért van mert a cross compiler
nagyon nagy, majdnem 10GB helyet foglal és ezért egy másik tárolóra helyeztem és nem voltam tisztában vele, hogy ezt a tárolót minden újraindításkor mountolni kell.

### Megoldás / tanulság
- Megcsináltam, hogy most már ne kelljen minden újraindításkor mountolni a hozzáadott tárhelyet:
    - A sudo blkid /dev/sdb1 paranccsal lekértem a tároló UUID-jét
    - Majd a sudo nano /etc/fstab paranccsal megnyitottam az fstab fájlt amibe beleírtam az új tároló szükséges adatait, így a rendszer automatikusan felismeri 

### Következő lépés
