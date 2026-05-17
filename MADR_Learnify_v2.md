# Learnify platform

## Context
Oktatási platform létrehozása különböző oktatási jellegű szolgáltatások nyújtására, igénybevételére.


## Decision drivers
3 fő attribútum együttes érvényesülése a cél:
    egyszerűség (átláthatóság, kezelhetőség)
    modularitás (domain separated)
    költséghatékonyság
Alapvetően strukturális és nem működési (operational) követelményekre épül a tervezés (Operational and Structural Measures-> Fundamentals of Software Architecture könyv 78-79. oldal). Jelen üzleti igény kapcsán versenyhelyzetet nem azonosítottam.


## Considered options
A lehetséges monolit vagy elosztott típusok (Fundamentals of Software Architecture könyv 123. oldal) közül az alábbi 3 alternatíva került megvizsgálásra. A moduláris jelleg (logikailag különálló egységek- Fundamentals of Sotfware Architecture könyv 38. oldal) és egyszerűség alapján kerültek kiválasztásra az alternatívák.
    Microservices Architecture Style
    Microkernel Architecture Style
    Service-Based Architecture Style

## Decision outcome
A 3 alternatíva közül a Service-Based Architecture (SBA) Style-ra esett a választás.
A kiválasztott architektúra ezen belül a monolit user interface felépítésen alapul (Fundamentals of Software Architecture könyv 214. oldal)

## Consequences

### Good
A Service-Based Architecture biztosítja a legoptimálisabban a
a modularitás, költséghatékonyság és egyszerűség együttes célrendszerét.
A Service-Based Architecture típusnak az egyszerűség és a költséghatékonyság a két fő mozgatórugója más
összetettebb, elosztott típusokkal szemben (Fundamentals of Software Architecture könyv 223. oldal) 
A modularitást hatékonyabban biztosítja, mint core és 
plug-in elemekre épülő mikrokernel típus, vagy mint a több adatbázisra épülő microservices típus.
A Learnify rendszer nem product-based application jellegű, illetve customization sem érintett, 
így egy mikrokernelnél egyszerűbb megoldás a Sevice-Based Architecture (Fundamentals of Software Architecture könyv 193. oldal) 
Egységek közötti kommunikáció jobb megvalósíthatósága (Mikrokernel rendszernél önálló plug-in komponensek->Fundamentals of Software Architecture könyv 198. oldal)
Kisebb számú egységgel megoldható a modularitás a Learnify esetén és erre megfelelőbb megoldás a Service-Based Architecture (Microservices esetén jobban lebontott/több kisebb egység->Fundamentals of Software Architecture könyv 330.oldal)
Moduláris jelleg külön fejlesztést és egyszerűbb migrációt tesz lehetővé (Advantages/Disadvantages-> Fundamentals of Software Architecture könyv 107. oldal, 210. oldal, 223. oldal), mely egy monolitikus rendszerhez képest előny
Learnify esetén egy adatbázis létrehozása a megfelelőbb, mert nincs túl sok külön egység (Microservices típus ezzel szemben teljes szátválasztásra, így külön adatbázisokra épül->Fundamentals of Software Architecture könyv 210. oldal és 333.oldal)


### Bad 
Külön modulok több fejlesztést igényelnek (monolit típushoz képest hátrány).
Elosztott rendszerek a monolit rendszerhez képest "általános jellegű" hátrányokkal is küzdenek 
(pl. hálózat megbízhatósága, biztonsága, latency -> Fundamentals of Software Architecture könyv 144-146. oldal)
Az egyszerűség és költséghatákonyság megvalósítása miatt egyes paraméterek kevésbé teljesítenek jól,
így például skálázhatóság. rugalmasság, hibatűrés (Fundamentals of Software Architecture könyv 223. oldal), míg ezek mikroservices
rendszer esetén kiválóan teljesítenek (Fundamentals of Software Architecture könyv 355. oldal)




