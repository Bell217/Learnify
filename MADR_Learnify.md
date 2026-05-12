# Learnify platform

## Context
Oktatási platform létrehozása különböző oktatási jellegű szolgáltatások nyújtására, igénybevételére.


## Decision drivers
3 fő attribútum együttes érvényesülése a cél:
    egyszerűség (átláthatóság, kezelhetőség)
    modularitás
    költséghatékonyság
Alapvetően strukturális és nem működési (operational) követelményekre épül a tervezés (Operational and Structural Measures-> Fundamentals of Software Architecture könyv 78-79. oldal). Jelen üzleti igény kapcsán versenyhelyzetet nem azonosítottam.


## Considered options
A lehetséges monolit vagy elosztott típusok (Fundamentals of Software Architecture könyv 123. oldal) közül az alábbi 3 alternatíva került megvizsgálásra. A moduláris jelleg (logikailag különálló egységek- Fundamentals of Sotfware Architecture könyv 38. oldal) és egyszerűség alapján kerültek kiválasztásra az alternatívák.
    Microservices Architecture Style
    Microkernel Architecture Style
    Service-Based Architecture Style

## Decision outcome
A 3 alternatíva közül a Service-Based Architecture (SBA) Style-ra esett a választás.

## Consequences

### Good
A Service-Based Architecture biztosítja a legoptimálisabban a
a modularitás, költséghatékonyság és egyszerűség együttes célrendszerét. 
A modularitást hatékonyabban biztosítja, mint core és 
plug-in elemekre épülő mikrokernel típus, vagy mint a több adatbázisra épülő microservices típus. 
Az egyszerűség és költséghatékonyság biztosítható oly módon, hogy nincs szükség ezek hátrányára
trade-off átváltásokra (Triangle-> Fundamentals of Software Architecture könyv 56-58. oldal).
Moduláris jelleg külön fejlesztést és egyszerűbb migrációt tesz lehetővé (Advantages/Disadvantages-> Fundamentals of Software Architecture könyv 107. oldal)

### Bad 
Külön modulok több fejlesztést igényelnek (monolit típushoz képest hátrány).




