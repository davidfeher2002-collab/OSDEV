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
