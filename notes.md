## GRUB bootloader használata

### Multiboot 2 szabvány

- Ez egy szabvány ami megmondja, hogy miket kell teljesíteni a bootloadernek és a kernelnek amit szeretnénk, hogy a bootloader betöltsön. Ilyenek például, hogy a multiboot header legyen a kernel első 8 kilobájtjában.

### Multiboot header

- Ez egy adatstruktúra amit a kernelben helyeznek el. A bootloader ennek segítségével ismeri fel, hogy ez egy betölthető kernel. A multiboot headernek 3 kötelező mezője van: magic number (pl: 0x1BADB002), flags, checksum -(magic + flags). Ennek a kernel fájl első 8 kilobájtjában kell elhelyezkedni és 4 bájtra kell igazítani. Ennek a három dolognak az összege együttesen 0 kell, hogy legyen.



