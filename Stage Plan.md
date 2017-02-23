**Kasutajad**

Need kasutajad, kellel on õigus muuta channel listi ja/või projekti, saavad muuta ka stage plan’i. Teistel projektikasutajatel on õigus stageplan’i ainult vaadata.

**Stageplani eesmärk**

Anda edasi pillide optimaalselt/sobilikku/vajalikku paigutust laval. Pillide paigutust mõjutab lavasuurus, akustika ja muud tegurid. Stageplani geneerimise aluseks on raideris esinevad pillid ja objektid.

**Olemid-atribuudid**

Stage plan

	Geneerimise_aeg

	Geneerimise_kp

	Muutmise_aeg

	Muutmise_kp

	Kes_viimati_muutis

	Pikkus

	Laius

	Custom_boolean

	Background_img

	Locked_boolean

Stage plan object

	Object_name

	X_coord

	Y_coord

	Comment

	Img

	Visible

**Seosed teiste registritega**

Users - 1...n - Kasutajad, kellel ligipääs projekti, on ligipääs ka stageplanile. (Sõltuvalt õigustest saadakse stageplani kas ainult lugeda, muuta.). 

Channel_list - 1 - Iga channel_list on (kaudselt) seotud ühe stage planiga.

Raider- 1 - Iga raider on seotud ühe stageplaniga.

Rights 1...n  - Igale kasutajale on teatud õigused stage plani suhtes suhtes (lugemine, muutmine).

Invite - 0...n - Igal channel list võib olla seotud invite’tega, mis saadetud välja kasutajatele, keda soovitakse siduda antud channel listiga.

Project 1 - Iga stage plan on ühe seotud projektiga (läbi raideri).

**Põhilised sündmused ajas**

-

**kasutusjuhud (nimi, kasutajad, eesmärgid, info****vaated****, uml+mockupid)**

Stage plani esmane genereerimine

	Kasutajad, kellel on õigus raiderit luua ja muuta

		Esmakordsel raideri loomisel projekti süsteem geneerib automaatselt stageplani. Samuti kui tehakse muudatusi raideris, siis need kajastuvad stage planis. Sh. pillide lisamine või eemaldamine raiderist. Kui geneeeritud stage planis tehakse muudatusi, siis see on custom olekus stageplan, millele ei mõju tehtud muudatused (kuni ei taastata algne raiderist lähtuv olek)

			Infovaade: stageplan view

Näiteks:

1. Kasutaja loob projekti

2. Kasutaja sisestab projeki raiderisse instrumente.

    1. Süsteem geneerib instrumentide alusel stage plani, kasutades objekte raideris.

3. Kasutaja teeb projekti raideris muudatused

    2. Süsteem teeb vastavad muudatused stage plan’il juhul, kui stage plan pole custom olekus.



Stage plani muutmine

	Kasutajad, kellel on õigus stage plani muuta

		Muutmise vajadus võib ilmneda stageplani objektide eemaldamises, nende visuaalse kuju muutmises (ikoonide muutmine), kommentaariide andmine objektidele.. Teatud muudatused annavad stage plani objektidele custom oleku st. muudatuste tegemisel raideris jäävad custom olekuga objektid muutmatuks.

			Infovaade: stageplan view

Näiteks:

1. Kasutaja muudab stage planis ühe objekti nime, muudab ühe objekti nähtavust, lisab kommentaare objektile, lisab juurde objekte mida raider ei ole, muudab raideri taustapilti jne.

2. Muudatused salvestatakse süsteemi poolt. Teatud muudatused annavad objektile custom oleku (sh nimemuutus, asukoha muutus, kommentaarid, nähtavus)

Stage plani lukustamine/lahtilukustamine

Kasutajad, kellel on õigus stageplani muuta

Stage plani lukustamine tähendab, et muudatused raideris ei kajastu stage planil. Lahtilukustamisel uued muudatused kajastuvad uuesti stage planil. Algselt on kõik stageplanis lukustamata olekus.

Infovaade: stageplan view

Näiteks:

1. Kasutaja lukustab stage plani

2. Kasutaja teeb muudatusi rideris

3. Minnes stage plani vaatesse, ei ole stage plan muutunud. Kasutajale kuvatakse teade, et "changes are pending/are not applied vms because stageplas is locked".



Stage plani sharemine

	Kõik kasutajad, kellel stage plani suhtes (vähemalt) lugemisõigus

Võimalus süsteemist välja eksportida pdf kujul channel list. Stage plani jagamine toimub PDF kujul. Kasutaja sisestab emaili, millele shareitakse stage plan.

Infovaade: funktsionaalsus on stage plani vaates.

Stage plani algoleku taastamine

Admin õigustega projekti kasutaja

Kasutaja saab taastada algse seisundi stageplanil (st. selline, mis on raideri põhjal tehtud). Taoline vajadus võib tekkida, kui kasutaja ei soovi enda poolt tehtud muudatusi üldse.

	infovaade: selleks on nupp "Revert to default" vms stage plani vaates

Näiteks:

1. Kasutaja soovib taastada algse oleku, vajutades "revert to default"

2. Süsteem küsib kinnitust

3. Kasutaja kinnitab

4. Süsteem taastab default oleku. St. kõik objektide nimed saavad raideris olevate objektide nimed, asukohad muutuvad algseteks, varjatud objekte enam ei varjata, raideris mitte olevaid objekte aga stageplanis olevad objektid kustutatakse, tausta pilt eemaldatakse, lukustatud olek võetakse maha jne.

