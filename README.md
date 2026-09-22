# Gamma Vezerlő 🖥️

Egyszerű Windows GUI eszköz a monitor gamma / fényerő / szaturáció / színhőmérséklet finomhangolásához, a Windows beépített `SetDeviceGammaRamp` API-ján keresztül — külső driver vagy monitor-szoftver nélkül.

![Platform](https://img.shields.io/badge/platform-Windows-blue)
![PowerShell](https://img.shields.io/badge/PowerShell-5.1%2B-5391FE)

## Miért készült?

Sok monitoron/laptopon nincs kényelmes beépített eszköz a gamma és a színhőmérséklet gyors állítására anélkül, hogy a Windows Beállítások mélyére kellene ásni, vagy egy nehézsúlyú gyártói szoftvert kellene telepíteni. Ez egy pár száz KB-os, egyetlen mappában futó alternatíva.

## Funkciók

- 🎚️ Csúszkás vezérlés: **Gamma**, **Fényerő**, **Szaturáció**, **Színhőmérséklet** (meleg ↔ hideg)
- 🖥️ Több monitor egyszerre (`EnumDisplayDevices` + gamma-rámpa minden aktív kijelzőre)
- 💾 **Profilok** mentése / betöltése / törlése (pl. "Filmnézés", "Munka", "Játék")
- ⌨️ Globális gyorsbillentyűk (működnek teljes képernyős alkalmazásban/játékban is):
  - `Ctrl + Alt + G` — ablak elrejtése / előhozása
  - `Ctrl + Alt + ↑` / `Ctrl + Alt + ↓` — fényerő gyors léptetése
- 🔁 Legutóbbi beállítás automatikus visszatöltése induláskor
- ✅ Kilépéskor automatikusan visszaállítja az alapértelmezett gamma-értékeket

## Telepítés / használat

1. Töltsd le / klónozd a repót.
2. Indítsd el a `Gamma Vezerlo.bat` fájlt.
3. Az első indításkor létrejön az Asztalon egy parancsikon is, a program saját ikonjával — ez automatikusan frissül akkor is, ha máshova másolod a mappát.

Nincs szükség telepítésre, rendszergazdai jog sem kell — a gamma-rámpa állítása normál felhasználói jogosultsággal is működik.

## Követelmények

- Windows 10 / 11
- PowerShell 5.1 (Windows-szal alapból jön)

## Mappa felépítés

```
GammaVezerlo/
├── Gamma Vezerlo.bat      # Indító
├── gammagui.ps1           # Fő GUI alkalmazás
├── mkshort.ps1            # Asztali parancsikon generátor (automatikusan lefut)
├── make_ico.ps1           # Ikon generáló script (ikon.png -> gammagui.ico)
├── ikon.png                # Forrás logó
├── gammagui.ico             # Alkalmazás ikon (több felbontásban)
└── profilok/                # Ide kerülnek a mentett profilok
```

## Figyelmeztetés

A gamma-rámpa módosítás rendszerszintű, minden futó alkalmazásra hat (nem csak a Gamma Vezerlőre). Ha valami extrém beállítást mentesz el és nem tudod visszaállítani, zárd be a programot (ez visszaállítja az alapértéket), vagy indítsd újra a gépet.

## Licenc

Szabadon felhasználható, módosítható, továbbfejleszthető.
