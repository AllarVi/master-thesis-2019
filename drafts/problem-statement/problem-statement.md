# Data driven gymnastics skills recognition and analysis - Andmepõhine võimlemisoskuste tuvastus ja analüüs

## Sissejuhatus

Võimlemine on pika ajalooga spordiala, mis arendab füüsilist jõudu, koordinatsiooni, kiirust, painduvust ja graatsiat. Arenema hakkas see ala juba Vana-Kreeka ajal, mil võimelmisharjutusi kasutati näiteks leegionite ettevalmistamiseks sõjaks. Meeste võimlemine oli kavas esimestel nüüdisaja olümpiamängudel aastal 1896. Aastast 1924 on võimlemine olnud tänapäevani olümpiamängude kavas[1]. Selle ajaga on võimlemises tekkinud palju harusid nagu näiteks iluvõimlemine, sportvõimlemine, sportakrobaatika jt. Võimlemise põhiharjutused on mõjutanud ja inspireerinud mitmeid uuemaid spordialasid. Näiteks ekstreemspordialadel tuntud pöörded üle horisontaal- ja vertikaaltelgede nõuavad harrastajalt sarnaseid füüsilisi atribuute nagu on võimlemises vaja tahasalto tegemiseks. 

Võimlejad ja nende treenerid teavad, et selliste keeruliste harjutuste tegemiseks on vaja vastata füüsikaseadustele. Nähtuseid nagu inerts, impulss, pöörlemine ja optimaalne tõukenurk tunnetab võimleja igapäevaselt ja valetehnika tunneb kogenud treener tänu kognitiivsele mustrituvastusele üpris kiiresti ära. Siiski, võimleja spordiajaloo dokumenteerimine, tehnika analüüsimine ja tagasiside andmine nõuab treeneritelt individuaalset keskendumist ja tähelepanu. Seega, harjutuste tehnika õpetamine ja korrigeerimine on olnud ja jääb ilmselt treenerite leivaks veel pikaks ajaks, sest tehnoloogilisi lahendusi, mis asendaks treenerite kogemust tänapäeval veel pole. See magistritöö tahab aidata kaasa masina loomisele, mis aitaks treeneritel ja võimlejatel automatiseerida isikliku spordiajaloo dokumenteerimist ja analüüsida harjutuste tehnikas vigu, mida võimleja ise ei tunneta või milleks treeneritel aega pole.

## Kontekst ja probleemipüstitus

Selleks, et masin saaks kaasa aidata tehnika parandamisele, peab see esmalt suutma tuvastada harjutused, mida atleet sooritab. Enne tuvastamist on aga vaja inimese liikumine digitaalselt salvestada. Inimese liikumise digitaalse salvestamise meetodid saab jämedalt liigitada kaheks: (a) **optilised meetodid** - näiteks paljudele meelelahutusmaailmast tuntud *motion capture* ja (b) **mitte-optilised meetodid** - erinevad kantavad seadmed (näiteks nutikellad), mis salvestavad keha kiirendust, rotatsiooni ja ülekoormust (*g-force*). 

Digitaalse salvestamise meetodite puhul seab autor eelduse, et see oleks ka praktikas rakendatav. See on võimlemise seisukohast oluline, sest paljude levinud harjutuste kombinatsioonid nõuavad tihtipeale kuni mitukümend meetrit vaba ruumi. Harjutused nagu rondaat[2], mida atleet kasutab horisontaalse kiiruse muundamiseks vertikaalseks kiiruseks vajavad mõned meetrid ruumi ning eeldavad, et atleedi kehale pole rakendatud väliseid piiranguid. 

See välistab juhtmeterohked, piiravad ja olulist lisakaalu tekitavad mitte-optilised sensorid. Lisaks, välistavad sellised piirangud ka *motion capture* maailmas tuntud markeeritud meetodid. Näiteks on uurimuses [3] tuvastatud algaja ja kogenud võimleja erinevused tehnikas ja selleks on kasutatud keha ühele küljele paigaldatud markereid. Kuigi põhjalik ja huvitav uuring, siis jätab selline meetod analüüsist välja kahe kehapoole lahknevused ning pakutud meetod pole ka **igapäevaselt** kasutatav. Käesoleva töö autor eeldab, et igapäevaseks analüüsiks pole võimlejad huvitatud erilisest markeeritud kostüümi selga tõmbamisest.

Oskused, mida võimleja peab valdama harjutuste sooritamiseks on näiteks oskus genereerida kõrgust (tuleneb vertikaalsest kiirusest tõuke hetkel) ja oskus õhus pöörata (tuleneb atleedi oskusest arendada ja kontrollida pöörete impulsimomenti). Selliseid ja veel teisi võimlemises vajaminevaid biomehaanilisi oskusi on varasemalt palju uuritud [3][4][5][6]. Eelnimetatud uurimused lähenevad võimlemise biomehaanika analüüsimisele juhtumiuuringu (*case study*) meetodil ja uurivad üldiselt detailsemalt ühte kindlat harjutust. Eraldi on välja toodud ka soov kasutada interaktiivseid, lihtsalt kasutatavaid ja simulatsiooni optimeerivaid tarkvara pakette. Rõhutud on kerget kasutatavust ja individuaalset sisendit lubavat tarkvara[4]. Just seda käesoleva magistritöö autor saavutada soovibki.

Rakenduslikust vaatenurgast lähtudes peaks pakutud biomehaanika analüüsimise lahendus olema atleedi individuaalsete parameetritega arvestav (näiteks kehaosade pikkuste suhted, mass ja riided). Sporditulemuste analüüsiks pakutav lahendus peaks olema distantsilt jälgiv, mitte-markeeritud ja kolmemõõtmelise kehaga arvestav süsteem[7].

Esimeseks uuritavaks probleemiks seab autor biomehaaniliste liigutuste segmenteerimise ja tuvastamise. Kuna võimlemise näol on tegemist keeruliste biomehaaniliste liikumistega, siis sobib võimlemisoskuste tuvastamine hästi väljatöödeldava meetodi valideerimiseks. 

Teiseks probleemiks seab autor tuvastatud liigutuste tõlgendamise ja tagasiside andmise tarkvara paketi kasutajale. Väljatöödeldava lahenduse saab lugeda õnnestunuks kui võimlemismaailma uurijad ja praktikud - treenerid ja atleedid hindavad lahenduse igapäevaselt kasutatavaks ja arusaadavaks.

## Töö ülesehitus

Autor plaanib läheneda võimlemisoskuste analüüsimise probleemile võimalikult tänapäevaste lahendustega. Viimastel aastatel on ilmunud uuringuid, kus kasutatakse inimese poosi tuvastamiseks masinõppelisi meetodeid. Näiteks avaldati aastal 2015 artikkel, kus kasutatakse inimese poosi tuvastamiseks videos konvolutsioonneuraalvõrke[8]. Sellised meetodid ületavad varasemad tipptasemel tehnikad oma täpsuse osas. 

Hiljem on ilmunud veel täiuslikumad meetodid, mis lubavad tuvastada inimese poose ka reaalajas. Näiteks kasutatakse sellist meetodit nagu *Part Affinity Fields* - sisuliselt hulk vektoreid, mis kodeerivad suuna jäseme ühest punktist teise. Iga jäset märgitakse afiinsusväljaga (ingl. *afinity field*) kehaosade vahel[9]. Sellist meetodit kasutab vaba lähtekoodiga tarkvara *OpenPose*[10]. OpenPose lubab tuvastada ühe inimese skeletti monokaameraga filmitud videost teiste inimeste juuresolekul. See võimaldab tuvastada atleedi skeletti ka keskkonnas, kus liiguvad taustal ringi teised inimesed (tavapärane vaatepilt võimlemiskeskustes).

// Esimese probleemi - tuvastusalgoritmi valik

// Teise probleemi - tuvastusalgoritmi tulemuste tõlgendus ja interpreteerimine

Käesoleva töö autor loodab ehitada praktiliselt kasutatava lahenduse toetudes eelnevatele töödele poosi hindamise *pose estimation* valdkonnas. Lisaks alternatiividega tuvumisele, plaanib autor kasutada võimlemisoskuste digitaalseks salvestamiseks vabavaralist tarkvara OpenPose.

Magistritöö praktilise osa üldine ülesehitus kulgeb järgnevalt:

1) Esmalt plaanib autor filmida nii algajaid kui ka kogenud atleete sooritamas võimlemisoskusi. 
2) Seejärel, kasutab autor vabatarkvaralist lahendust OpenPose atleedi skeleti digitaalseks salvestamiseks.
3) Skeleti digitaalsesest salvestusest tuleb vajalikud andmed ekstraheerida ja kasutada neid harjutuse **tuvastusalgoritmi** sisenditena. 
4) Tuvastusalgoritmi tulemused tuleb seejärel tõlgendada. Lisaks, võimlemisoskuste paremaks interpreteerimiseks proovib autor rakendada **keskmise trajektoori** meetodit[11]. Kaalutakse ka alternatiivseid meetodeid.
5) Väljatöötatud lahendus pakutakse katsetamiseks võimlemistreeneritele ja võimlejatele. Kui lahendus loetakse praktiliselt kasutatavaks, siis võib lugeda lahenduse õnnestunuks.
6) Viimase osana arutleb autor tulemuste üle ja pakub võimalusi lahenduse täiendamiseks.






