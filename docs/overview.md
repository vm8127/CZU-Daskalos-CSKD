# CSDK — Project Overview

**Autor:** Vladimír Martinovský  
**Systém:** Databáze knih (klon ČSFD)

---

## Třídy

| Třída | Atributy |
|-------|----------|
| `Author` | name, surname, birthday |
| `Book` | name, publicationYear, genre, author |
| `User` | username, registrationDate |
| `Rating` | book, user, value, comment |

## Custom metody (odvozené atributy)

| Třída | Metoda | Popis |
|-------|--------|-------|
| `Author` | `fullName` | name + surname |
| `Book` | `age` | stáří knihy (roky) |
| `Book` | `averageRating` | průměr hodnocení přes `Rating allInstances` |
| `Rating` | `isMasterpiece` | true pokud value >= 4 |

## Data (Script)

- 3 autoři: Orwell, Rowling, Francis
- 6 knih: 1984, Animal Farm, HP, Dead Cert, Nerve, Odds Against
- 3 uživatelé: john_doe, jane_doe, horse_fan
- 7 hodnocení

## Dotazy (Workspace)

1. `Books select: [:b | b author surname = 'Orwell']` — Book + Author
2. `Ratings select: [:r | r user username = 'john_doe']` — Rating + User
3. `Books select: [:b | b averageRating > 4]` — Book + Rating
4. Knihy s avg > 4 seřazené DESC
5. Všechny knihy seřazené podle avg ratingu DESC

---

## Kontrola zadání

| # | Požadavek | Splněno |
|---|-----------|---------|
| 4 | Min. 3 datové třídy | ✅ (4 třídy) |
| 5 | Min. 3 metody pro odvozené atributy | ✅ (fullName, age, averageRating, isMasterpiece) |
| 6 | Min. 3 dotazy přes více tříd | ✅ (dotazy 1–3 pokrývají Book+Author, Rating+User, Book+Rating) |
| 8 | Min. 3 instance každé třídy | ✅ (3, 6, 3, 7) |
| 9 | Objektové normální formy | ✅ (každá třída má vlastní atributy, vazby přes reference) |
