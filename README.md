# Projekat iz Verifikacije Softvera

**Autor:** Vuk Stefanović\
**Broj indeksa:** 1036/2024\
**Datum:** 18. februar 2025.

## Uvod

*The Legend of Zelda* je jedna od najpoznatijih i najuticajnijih video igara svih vremena, prvi put objavljena 1986. godine od strane kompanije Nintendo. Igra prati avanture Linka, mladog heroja koji kreće u epsku misiju kako bi spasio princezu Zeldu i zaštitio zemlju Hyrule od zlog Ganon-a. Serijal je poznat po svojoj inovativnoj mehanici istraživanja otvorenog sveta, složenim zagonetkama i dinamičnim borbenim sistemima. 

Svaka igra u serijalu kombinuje elemente akcije, avanture i rešavanja zagonetki, omogućavajući igračima da istražuju prostrane svetove, komuniciraju sa različitim likovima i sakupljaju moćne predmete. *The Legend of Zelda* je vremenom evoluirala, uvodeći naprednu fiziku, bogatu priču i složenije mehanike igranja, što ju je učinilo jednim od najcenjenijih naslova u istoriji igara.



Ovaj projekat analizira i verifikuje implementaciju igre *The Legend of Zelda* u programskom jeziku C++. Cilj analize je poboljšanje stabilnosti i efikasnosti aplikacije korišćenjem statičkih i dinamičkih alata za analizu koda.

Za verifikaciju koda korišćeni su sledeći alati:

- **Cppcheck** – statička analiza koda
- **Clang-Tidy** – analiza kvaliteta i optimizacije C++ koda
- **Doxygen** – generisanje automatske dokumentacije
- **Valgrind Memcheck** – analiza memorije i otkrivanje curenja memorije
- **Valgrind Callgrind** – profilisanje performansi i analiza efikasnosti koda

## Instalacija alata

Pre pokretanja analize potrebno je instalirati sledeće alate:

```bash
sudo apt install cppcheck
sudo apt install clang-tidy
sudo apt install doxygen
sudo apt install valgrind
sudo apt install kcachegrind
```

## Korišćeni alati i analiza rezultata

### 1. Cppcheck

Pre pokretanja, pozicionirati se u direktorijum projekta:

```bash
cd ../cppcheck
```

Pokrenuti Cppcheck sledećom komandom:

```bash
cppcheck --project=compile_commands.json --enable=all --std=c++20 -inconclusive --report-progress &> cpp_check_res.txt
```

### 2. Clang-Tidy

Pre pokretanja, pozicionirati se u direktorijum projekta:

```bash
cd ../clang-tidy
```

Pokrenuti Clang-Tidy sledećom komandom:

```bash
run-clang-tidy -checks='clang-diagnostic-*, clang-analyzer-*' .. &> clang-tidy-report.txt
```

### 3. Doxygen

Pre pokretanja, pozicionirati se u direktorijum projekta:

```bash
cd ../doxygen
```

Dati skripti odgovarajuće dozvole i pokrenuti je:

```bash
chmod +x run_doxygen.sh
./run_doxygen.sh
```

### 4. Valgrind Memcheck

Pre pokretanja, pozicionirati se u direktorijum projekta:

```bash
cd ../valgrind/memcheck
```

Dati skripti odgovarajuće dozvole i pokrenuti je:

```bash
chmod +x run_memcheck.sh
./run_memcheck.sh
```

### 5. Valgrind Callgrind

Pre pokretanja, pozicionirati se u direktorijum projekta:

```bash
cd ../valgrind/callgrind
```

Dati skripti odgovarajuće dozvole i pokrenuti je:

```bash
chmod +x run_callgrind.sh
./run_callgrind.sh
```

## Zaključak

Primena različitih alata za analizu koda omogućila je sveobuhvatnu proveru stabilnosti i efikasnosti aplikacije. Statičkom analizom pomoću **Cppcheck** i **Clang-Tidy** detektovane su sintaksičke greške, problemi sa memorijom i mogućnosti optimizacije koda. **Doxygen** je omogućio generisanje detaljne dokumentacije, olakšavajući razumevanje strukture projekta i njegovu dalju nadogradnju.

Dinamičkom analizom kroz **Valgrind Memcheck** identifikovani su problemi sa upravljanjem memorijom, poput curenja memorije i neoslobođenih alokacija, dok je **Valgrind Callgrind** omogućio uvid u performanse aplikacije, otkrivajući funkcije sa najvećim opterećenjem. Vizuelizacija podataka pomoću **KCacheGrind** pomogla je u identifikaciji uskih grla u izvršavanju koda.

Predložene optimizacije uključuju:
- **Bolje upravljanje memorijom** – smanjenje curenja i efikasnije oslobađanje resursa korišćenjem pametnih pokazivača (`std::unique_ptr`, `std::shared_ptr`).
- **Poboljšanje performansi** – optimizacija najčešće pozivanih funkcija, redukovanje broja realokacija memorije i efikasnije korišćenje STL kontejnera.
- **Unapređenje kodnog stila** – primena modernih C++ standarda, zamena zastarelih konstrukcija i optimizacija iteracija kroz strukture podataka.

Implementacija ovih poboljšanja ne samo da će povećati efikasnost i stabilnost aplikacije, već će i doprineti lakšem održavanju i skalabilnosti softverskog rešenja. Dalje unapređenje može se postići kontinuiranom analizom i iterativnim poboljšanjem identifikovanih problematičnih delova koda.



Unapređenje kodnog stila – primena modernih C++ standarda, zamena zastarelih konstrukcija i optimizacija iteracija kroz strukture podataka.

Implementacija ovih poboljšanja ne samo da će povećati efikasnost i stabilnost aplikacije, već će i doprineti lakšem održavanju i skalabilnosti softverskog rešenja. Dalje unapređenje može se postići kontinuiranom analizom i iterativnim poboljšanjem identifikovanih problematičnih delova koda.
