Tere,

Kirjutan Teile sooviga küsida nõu ja tagasisidet magistritöö teema valimisel. Magistriseminari kursuse raames tutvustasite ühe oma huvialana masinõppe ja inimese motoorika kombineerimist. Peale loengut andsite mulle mõned artiklid samal teemal, täpsemalt Parkinsoni tõve analüüsimise kohta. Teema oli huvitav ja mulle meeldis idee motoorika oskuste analüüsimise digitaliseerimisest ja automatiseerimisest masinõppe abil.

Vestluses mainisin, et otsin ise teemat, mis puudutaks sportliku biomehaanika analüüsimist. Näitena tõin erinevate akrobaatiliste elementide (nt. tagurpidi salto) tehnika analüüsimise automatiseerimise masinõppe abil. Pakkusite, et võib-olla saaks laboris inimesele mingid seadmed kinnitada ja nende abil liikumise kohta andmeid koguda. Edasi proovisin ise veidi rohkem teemasse süveneda ja uurida kuidas selliseid asju tehakse.

Leidsin mõned artiklid ja avastasin, et enam-jaolt tehakse taolisi analüüse peamiselt kahe meetodiga: (a) optilised meetodid nagu näiteks motion capture kaamerad ja (b) mitte-optilised meetodid nagu erinevad kantavad seadmed, mis sisaldavad endas kiirendusmõõtureid ja güroskoope. Kuid enamus nendest meetoditest pole eriti kaasaskantavad ja nõuavad eritingimusi. Leidsin viiteid ka edasiarendustele nagu markerless motion capture tehnikale, mis ei nõua enam spetsiaalse kostüümi selga panemist, kuid mis vajab 3D scannerit ja 6-te 2D kaamerat (1). See pole kuigi mobiilne ega odav. Kasutatakse ka marked-based motion capture ja IMUde (inertial measurement unit) kombineerimist, kuid vähemalt selles artiklis kasutatud meetodid tunduvad siiski liiga spetsiifilised ja vajavad eritingimusi ehk nö. tavatrennis on liiga keeruline kasutada (2). Muljetavaldavam on juba selline lihtne tehnika kus kasutatakse ainult ühte kantavat seadet. Kujutan ette, et taoline tehnika on paljudel inimestel juba kelladesse integreeritud ja nende abil saab päris palju huvitavat infot selliste populaarsete treeningute ja tehnika kohta nagu jooksmine, ujumine, jalgrattasõit (3). Sellise meetodi pluss on kindlasti lihtsus, aga miinus see, et ei kasutata tervet inimese skeletti ja seega on raskemate sporditehnikate analüüsimine vearohke. Sporditehnika analüüsimise automatiseerimine masinõppe abil on populaarne teema, kuid enamus minu leitud artiklid meenutavad siiski rohkem laborirottide analüüsimist 17 sensori ja spetskostüümiga, mis pole igapäeva elus väga korratav (4).

Suhtlesin ka ühe Rootsis õppiva sõbraga, kellega meil on ühine huvi biomehaanika uurimise vastu ja kes töötab igapäevaselt motion capture teenuseid pakkuvas ettevõttes. Vestlusest temaga tekkis idee, et kui lihtsaks ja kättesaadavaks oleks võimalik tänapäeval akrobaatiliste elementide analüüsimine teha.

Idee oleks kombineerida skeleti tuvastust video pealt koos ühe lihtsa kantava seadmega, mis sisaldaks güroskoopi ja kiirendusmõõturit. Mind suunati sellise tasuta tarkvara nagu https://github.com/CMU-Perceptual-Computing-Lab/openpose suunas, mis kasutab sisuliselt tavalist kaamerat ja tuvastab masinõppe abil üpris kergelt videolt inimese skeleti. Kui kombineerida taolise tarkvaraga kogutud andmed koos ühe kantava sensori andmetega, siis oleks võimalik treenida mõni masinõppe mudel, mis võiks esialgu vähemalt hakata tuvastama keerulisemaid akrobaatilisi elemente. Selline meetod tundub igapäevaselt lihtsalt kasutatav ja on oma odavuselt kättesaadav. 

Küsiksin, et kui magistritöö vääriline selline idee oleks? Kas selline töö oleks teostatav? Kuidas Teile tunduks sellise töö juhendamine või kas suunaksite mind kellegi teise juurde?

Vabandan pika kirja eest.

Lugupidamisega,
Allar Viinamäe


Mõned mainitud artiklid, mis ma leidsin:
(1) A markerless motion capture technique for sport performance analysis and injury prevention: Toward a ‘big data’, machine learning future
Alderson, J.
Journal of Science and Medicine in Sport, Volume 19, e79
(2) Stetter, B.J.; Ringhof, S.; Krafft, F.C.; Sell, S.; Stein, T. Estimation of Knee Joint Forces in Sport Movements Using Wearable Sensors and Machine Learning. Sensors 2019, 19, 3690.
(3) Daniel W.T. Wundersitz, Casey Josman, Ritu Gupta, Kevin J. Netto, Paul B. Gastin, Sam Robertson,
Classification of team sport activities using a single wearable tracking device,
Journal of Biomechanics,
Volume 48, Issue 15,
2015,
Pages 3975-3981,
ISSN 0021-9290,
https://doi.org/10.1016/j.jbiomech.2015.09.015.
(http://www.sciencedirect.com/science/article/pii/S0021929015005096)
(4) Jang, J.; Ankit, A.; Kim, J.; Jang, Y.J.; Kim, H.Y.; Kim, J.H.; Xiong, S. A Unified Deep-Learning Model for Classifying the Cross-Country Skiing Techniques Using Wearable Gyroscope Sensors. Sensors 2018, 18, 3819.
