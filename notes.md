## GRUB bootloader használata

### Multiboot header

- Ez egy adatstruktúra amit a kernelben helyeznek el. A bootloader ennek segítségével ismeri fel, hogy ez egy betölthető kernel. A multiboot headernek 3 kötelező mezője van: magic number (pl: 0x1BADB002), flags, checksum -(magic + flags). Ennek a kernel fájl első 8 kilobájtjában kell elhelyezkedni és 4 bájtra kell igazítani. Ennek a három dolognak az összege együttesen 0 kell, hogy legyen.
