# ADR-001: Milyen technológiával készüljön a TaskFlow?

**Státusz:** Elfogadva
**Dátum:** 2026-10-03

## Kontextus

A TaskFlow egy webes feladatkezelő lesz. El kell döntenünk, milyen nyelvet és eszközöket használunk, hogy mindenki tudjon rajta dolgozni.

## Döntés

- **Frontend:** React
- **Backend:** Node.js (Express)
- **Adatbázis:** PostgreSQL

Azért ezt választottuk, mert így elöl és hátul is JavaScript van, ezért csak egy nyelvet kell tudni. A felhasználók, projektek és feladatok összefüggnek, ezért jól illik hozzá egy SQL adatbázis.

## Alternatívák

- **C# / ASP.NET:** jó választás lett volna, de két nyelvet kellett volna használni, és kevesebben ismerjük.
- **MongoDB:** egyszerűbb indulni vele, de a táblák közti kapcsolatokat SQL-ben könnyebb kezelni.

## Következmények

- (+) Egy nyelv az egész projektben.
- (+) Sok leírás és példa érhető el hozzá.
- (−) A frontendet és a backendet külön kell elindítani.
