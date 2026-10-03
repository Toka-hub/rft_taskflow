# Nem funkcionális követelmények

| ID | Kategória | Követelmény |
|----|-----------|-------------|
| NFR-1 | Teljesítmény | A feladatlista legfeljebb 2 másodperc alatt töltődjön be 500 feladatot tartalmazó projekt esetén is; a rendszer legalább 50 egyidejű felhasználót szolgáljon ki lassulás nélkül. |
| NFR-2 | Biztonság | A jelszavakat a rendszer csak hash-elve tárolja (pl. bcrypt); a jelszó legalább 8 karakter és tartalmaz számot. A felhasználók csak azon projektek feladatait látják, amelyeknek tagjai. |
