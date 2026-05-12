# Learnify
E-learning platform/Software architecture design
## Documents

### Architecture Characteristics Worksheet

### MADR

### C4 diagrams

## Description/Process
Első lépés: 

    Releváns attribútumok kiválasztása
    3 fő attribútum beazonosítása

Második lépés:

    A 3 fő attribútum együttesen mely architektúrához illeszkedik a legjobban.

    3 vizsgált alternatíva: 
        Microservices
        Service-Based Architecture
        Mikrokernel
    
    Microservices: 
        domain alapú (e tekintetben megfelel a funkcionális szétválasztási követelménynek)
        modularity a legjobb besorolási kategória alá tartozik
        minden szolgáltatáshoz külön adatbázis (ez szükségtelen)
        költségvonzata a leggyengább besorolási kategória alá esik
        egyszerűség szempontjából is a leggyengébb besorolási kategória alá esik

    Mikrokernel:
        domain alapú a plug-in alapján (funkcionális szétválasztásnak megfelel)
        van egy core elem és ennek hibája az egész rendszerre hatással van
        a modularity így ennél a típusnál már csak közepes értékelést kap
        költséghatékonyság a legjobb kategória alá tartozik, jelentős előny microserviceshez képest
        kevésbé komplex, mint microservices, így közepes értékelést kap egyszerűség tekintetében

    Service-Based Architecture:
        logikai egységek szétválasztása/domain szerinti szeparáció itt is a modell alapja
        a modularitás jó kategória alá esik (mikokernel és microservices között helyezkedik el)
        költségvonzata is a jó kategória alá esik
        egyszerűság szempontjából közepes értékelés alá esik 

    Értékelés ereménye:
        A választás azért esett a Service-Based Architecture típusra, mert a modularitást
        megfelelőbben biztosítja, mint a mikrokernel és a tényleges funkciók várhatóan nem változnak.
        Minden besorolható az SBA típus alapján felépített 4 fő modulba, így nem látok célszerűnek egy plug-in rendszert.
        Microservices pedig a költségvonzata és komplexitása miatt nem reális alternatíva.

Harmadik lépés:
    A kiválasztott Service-Based Architecture Style C4 diagram ábrázolása.
    Modulok alapján 4 fő konténer:User,Course,Exam,Database.
    A modulokon belül vannak az ezekhez kapcsolódó egyes események (pl.jelentkezés)
    SystemContext és Container diagramok.
