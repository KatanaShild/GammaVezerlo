# Gamma Vezérlő 🖥️

Kijelző színbeállító játékhoz: vibrance, szaturáció, gamma, fények/árnyékok és még sok más — egyetlen kis `.exe`, telepítés nélkül.

## Indítás

1. Csomagold ki a zipet egy normál mappába (pl. Dokumentumok, ne a zipből futtasd).
2. Indítsd a **`GammaVezerlo.exe`**-t. Rendszergazdai jog nem kell.
3. Ha a Windows SmartScreen figyelmeztet („A Windows megvédte a számítógépét"): **További információ → Futtatás mégis**. Az `.exe` nincs digitálisan aláírva, ezért kérdez rá. (Alternatíva: jobb klikk az `.exe`-n → Tulajdonságok → „Feloldás".)

## Amit tud

- 🎚️ **Vibrance** (0–100% NVIDIA driver, 100–350% szoftveres) és **Szaturáció** (0–300%)
- 🎛️ **Finomhangolás:** Fényerő, Kontraszt, Fények, Feketék, Árnyék árnyalat, Gamma, Hőmérséklet, Árnyékok, Fehérek, Fény árnyalat
- 🎞️ **Jelenetek:** beépített look-ok + saját mentett look-ok
- 📤 **Megosztás kóddal:** a „Kód másolása" egy rövid `GV1-…` kódot ad a vágólapra; akinek elküldöd, a „Beillesztés" gombbal betölti pontosan ugyanazt a beállítást
- 🔔 **Tálca-ikon:** az ablak bezárása (X) a tálcára küldi a programot, a hatás közben megmarad. Jobb klikk az ikonra: Megnyitás, Eredeti kép, Jelenetek (gyorsváltás), Indítás Windowsszal, Kilépés. Dupla kattintás az ikonra: ablak ki/be
- 🚀 **Indítás Windowsszal** (a tálca-menüből vagy az ablak alján lévő gombbal) — a tálcára indul, ablak nélkül
- 🔒 Egyszerre csak egy példány fut; ha másodszor indítod, az elsőt hozza elő
- ⌨️ Globális gyorsbillentyűk (játék közben is): `Ctrl+Alt+G` ablak, `Ctrl+Alt+↑/↓` vibrance, `Ctrl+Alt+O` eredeti kép ki/be
- Csúszkán: dupla kattintás = alapérték, egérgörgő / nyílbillentyűk = finom léptetés
- Kilépéskor minden visszaáll az alapértékre

## Hol tárolja az adatait?

`%AppData%\GammaVezerlo\` (beírhatod a Windows Fájlkezelő címsorába)

- `profilok\` — a mentett look-ok (`.json`)
- `allapot.json` — az utolsó beállítás
- `hiba.log` — csak ha váratlan hiba történt

A régi (PowerShell-es) verzió `profilok` mappáját és `allapot.json`-ját a program az első indításkor automatikusan átveszi, ha az `.exe` mellett találja.

## Eltávolítás

Kapcsold ki az „Indítás Windowsszal"-t, lépj ki a programból, majd töröld a mappát (és ha akarod, a `%AppData%\GammaVezerlo` mappát).

## Újrafordítás (opcionális)

A `forras\` mappában van a teljes forráskód. A `forras\epit.bat` a Windowsba beépített .NET Framework 4 fordítójával újraépíti a `GammaVezerlo.exe`-t — semmit nem kell telepíteni.

## Ismert korlátok

- Az NVIDIA-vibrance csak akkor él, ha a kijelző az NVIDIA GPU-ra van kötve. Hibrid grafikájú laptopon a belső kijelző általában az Intel GPU-n van, ilyenkor a program szoftveres vibrance-ra vált (a státuszsor kiírja).
- A szaturáció / fényerő / kontraszt / hőmérséklet (színmátrix) exkluzív teljes képernyős játékban nem látszik, csak ablakos vagy borderless módban. A gamma-görbe (fények, árnyékok, stb.) és az NVIDIA-vibrance ettől független.
- A gamma-görbe módosítás rendszerszintű; ha bármi elromlana, a program bezárása visszaállítja az alapértékeket.
