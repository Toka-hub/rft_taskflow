# ADR-001: Technológiai stack kiválasztása

- **Státusz:** Elfogadva
- **Dátum:** 2026-10-03
- **Érintettek:** TaskFlow csapat

## Kontextus

A TaskFlow egy webes feladatkezelő alkalmazás (feladatok létrehozása, listázása, állapotváltás, felelős hozzárendelése). A csapatnak olyan technológiát kell választania, amely:

- gyorsan megtanulható, és a csapattagok egy része már ismeri,
- támogatja a REST API-n alapuló kliens–szerver felépítést,
- relációs módon tudja tárolni a felhasználók, projektek és feladatok közti kapcsolatokat,
- teljesíti a nem funkcionális követelményeket (NFR-1: 2 mp alatti betöltés, NFR-2: hash-elt jelszavak, jogosultságkezelés).

## Döntés

Háromrétegű webes architektúrát használunk:

| Réteg | Technológia |
|-------|-------------|
| Frontend | React (Vite) |
| Backend | Node.js + Express, REST API |
| Adatbázis | PostgreSQL |

A frontend és a backend is JavaScriptben (TypeScriptben) készül, így a csapat egy nyelvvel dolgozik.

## Mérlegelt alternatívák

| Alternatíva | Miért nem ezt választottuk |
|-------------|----------------------------|
| ASP.NET Core + Angular | Erős, de két különböző nyelv (C#, TypeScript), nagyobb tanulási idő. |
| Python (Django) szerveroldali sablonokkal | Gyors indulás, de kevésbé interaktív felület, és nem válik szét a frontend és a backend. |
| MongoDB adatbázis | A projekt–felhasználó–feladat kapcsolatok relációsak, SQL-ben egyszerűbb kezelni őket. |

## Következmények

**Előnyök**
- Egy nyelv a teljes stackben, a csapattagok bármelyik rétegen tudnak dolgozni.
- A REST API miatt a frontend és a backend külön fejleszthető és tesztelhető.
- A PostgreSQL biztosítja az adatok konzisztenciáját (idegen kulcsok, tranzakciók).

**Hátrányok / kockázatok**
- Két külön alkalmazást kell futtatni és telepíteni (frontend és backend).
- A jelszókezelést és jogosultságot nekünk kell megvalósítani (pl. bcrypt, JWT).

## Kapcsolódó dokumentumok

- `docs/architecture/use-case.png`, `sequence.png`, `class.png`
- `docs/nem-funkcionalis-kovetelmenyek.md`
