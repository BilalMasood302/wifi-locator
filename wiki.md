AVTORJA:
Robert Pavlovič,
Dorijan Morelj

NASLOV PROJEKTA: '''WiFi INDOOR LOCATING'''

Izvorna koda in **.apk: https://code.google.com/p/wifi-locator/issues/detail?id=1**


[[File:Indoor-navigation.jpg]]


'''1. PREDSTAVITEV IDEJE:'''

Najin projekt je android aplikacija s katero bi lahko v neki znani zgradbi pomagali obiskovalcem, z prikazom njihove trenutne lokacije in prikazom poti do cilja.


'''2. NASTAVITEV VIRTUALNE MACHINE:'''

•	Zaslon: 4.0" WVGA (480\*800), ležeča postavitev

•	Nexus One by Google 4.0"

•	Android 4.0.2

•	Ram 512 MB

•	HDD 200 MB

•	SD CARD 1024 MB

KASNEJE:
Uporaba android plošče, ki smo jo uporabljali na vajah in navadne android tablice.


'''3. NAČRT DELA:'''

3.1. Idejo razbiti na manjše obvladljive kose ter jih preučiti kakšna bi bila hitra in učinkovita realizacija

3.2. Preveriti kakšna je podpora knjižnic in metod, s katerimi bi lahko manipulirali WiFi vmesnik in pregled obstoječih izvornih kod aplikacij.

3.3. Programiranje najbolj pomembnih delov in preverjanje njihovega delovanja

3.4. Sestava posameznih delov v celoto in testiranje

3.5. Pregled omrežja, merjenje moči omrežja, določanje odmika med točkami, da se jasno vidi razlika v moči omrežja

3.6. Izdelava celotne aplikacije

3.7. Urejanje grafičnega vmesnika


'''4. DNEVNIK DELA:'''

[[Ponedeljek, 15.4. 2013]]

•	Izbira ideje, kratka analiza idej

[[Ponedeljek, 22.4. 2013]]

•	Risanje načrta, pretvorba ideje v vmesne obvladljive dele, razvijanje koncepta

[[Ponedeljek, 6.5. 2013:]]

•	Risanje shem, menija, določitev activitjev, funkcionalnost posameznih activitijev, prehodi med activitje
•	Postavitev gonilnika za Olimex

[[Ponedeljek, 13.5.2013:]]

•	Testiranje aplikacij kot so WiFidemo in ostalih, odpravljanje napak z dovoljenji(permissions) za uporabo WiFi-ja

[[Torek, 14.5.2013]]

•	Pregled wifi paketa, metod, raznimi parametri(SSID, BSSID, LEVEL, FREQUENCY)

[[Sreda, 15.5.2013]]

•	Postavljanje teoretične relacije med NetworkPointom in Networkom.
•	NetworkPoint je objekt, ki predstavlja točko na zemljevidu, vsebuje obe koordinati x in y, in seznam objektov tipa Network. To so vsa omrežja z svojimi parametri na določeni     lokaciji.
•	Network je objekt, predstavlja pa neko omrežje z parametri: SSID, BSSID, moč signala in frekvenca.
•	Pisanje lastnih objektov NetworkPoint in Network, njihovih konstruktorjev, setterjev in getterjev.

•       NetworkPoint:

[positionX, positionY, lista networks tipa Network ](.md)

•       Network:

[SSID, BSSID, deciBels, frequency, positionX, positionY ](.md)

[[Ponedeljek, 20.5.2013]]

•	Testiranje WiFiscana in ostalih aplikacij, branje dokumentacije, učenje pisanja aplikacij katere smo imeli na vajah
•	pisanje razreda in metod s katerimi bi pridobili vrednosti iz omrežja
•	odpravljanje napak povezanih s dovoljenji
•	odpravljanje napak s kodo

[[Torek, 21.5.2013]]

•	pisanje objektov tipa NetworkPoint in Network, pisanje konstruktorjev, seterjev, geterjev postavitev layoutov in lastnosti posameznih elekemtov
•	pisanje funkcij za zapis omrežij v datoteki txt v kateri hranimo vse potrebne parametre v datoteki txt - podobna CSV datoteki s tem da je separator "_"
•	odpravljanje napak povezanih z odpiranjem in zapiranjem datotek_

[[Sreda, 22.5.2013]]

•	pisanje funkcije za branje omrežij iz txt datotek - parser
•	pisanje funkcije za branje omrežij in tvorjenje objektov tipa NetworkPoint in Network
•	postavljanje try, catch blokov in lovljenje izjem
•	odpravljanje raznih napak

[[Četrtek, 23.5.2013]]

•	pisanje funkcionalnosti, ki prenese vrednosti med activity
•	pisanje funkcije, ki pretvori iz dB v neko pozitivno število na intervalu od 0 do 100
•	pisanje funkcije za spinner in izbiro vrednosti
•	odpravljanje napak

[[Sobota, 25.5.2013]]

•	popravljanje id-jev v xml, R classu, itd
•	pisanje funkcije za odziv na tipke
•	pisanje funkcije za serializacijo objektov med activity-i
•	pisanje funkcije, ki s pomočjo trenutne pozicije izračuna na podlagi kvadrata najmanjše razdalje približno lokacijo
•	popravljanje kode

[[Sobota, 1.6.2013]]

•	popravljanje večjega dela aplikacije
•	brisanje funkcij za delo z txt datotekami
•	brisanje funkcij za delo z objekti tipa NetworkPoint in Network
•	branje dokumentacije in uvedba SQL lite baze
•	odpravljanje napak

[[Nedelja, 2.6.2013]]

•	pisanje funkcij za dodajanje omrežij v bazo
•	pisanje funkcij za branje omrežij iz bazo

[[Ponedeljek, 3.6.2013]]

•	pisanje funkcij računanje trenutno lokacije s pomočjo baze
•	odpravljanje napak

[[Četrtek, 6.6.2013]]

•	odpravljanje napak povezanih s prikazom slik kurzorjev trenutne lokacije in cilja na zemljevidu

[[Petek, 7.6.2013]]

•	Izdelava activitya, ki ustvari SQLite podatkovno bazo in v njo na pregleden način shranjuje informacije, ki pripadajo posamezni točki

•       SQLite tabela(ssid1-3 = BSSID dostopne točke, rssi1-3 linearizirana moč signala, X & Y koordinate meritve):
> _id ssid1             ssid2             ssid3             rssi1 rssi2 rssi3 X  Y
  1. 00:0f:f7:2d:fe:d0 de:71:44:2e:9a:7d 68:7f:74:10:a9:55 81    77    70    17 8
> 2   00:0f:f7:2d:fe:d0 00:11:5c:c7:20:c0 00:17:f2:e1:59:77 92    72    70    13 11
> 3   00:11:5c:c3:8b:d0 c8:3a:35:f3:b0:78 00:1c:10:a4:20:6e 88    77    70    7  11
> ..._

[[8.6](Sobota.md)]

•	dodelava SQLite activitya in dodajanje algoritma, da vrne X in Y koordinato glede na meritve omrežja


'''5. MAPIRANJE'''

Ročno sva poslikala tlorise fakulteta, ter jih kasneje prerisala v vektorsko sloko, pri tem sva dimenzije ohranila sorazmerne realnim dimenzijam.
Nato sva izvedla postopek mapiranja, tako da sva označila mrežo točk na tlorisu in po teh točkah pomerila omrežje.
Zato sva uporabljala activity v katerem sva osveževala omrežje in podatke vključno s koordinatami shranjevala v podatkovno bazo.
Tako sva za vsako točko lahko določila seznam prisotnih omrežij, ki jih ločimo po SSID ali pa bo BSSID-ju ter glede na moč signalov, kar je naš enolični idetifikator posamezne točke.

Metoda getScanResults vrne seznam omrežij z pomembnimi parametri, kot so SSID, BSSID, moč v decibelih, na kar preslikamo moč signala na linearen interval 0-100. Nižja negativna vrednost v decibelih pomeni močnejši signal, najmočnejši signali(tik pri anteni) so bili moči -57dB, Ko pa enkrat presežemo -95dB pa se povezava izgubi.


[[File:Screenshot 2013-06-10-17-57-09.png]]


'''6. KAKO DELUJE LOCIRANJE  '''

Deluje tako, da vstopimo v prostor na fakulteti in android napravi omogočimo Wi-Fi povezavo nato pritisnemo gumb Scan in nato MyLocation, kar nam  poskenira celotno omrežje in prikaže lokacijo, ki ima največ ujemanj v naši bazi. V primeru, da je število ujemanj enako pokaže zadnjo točko.

Najprej preveri ujemanja najmočnejšega BSSIDja, če je ujemanj več kot 1 preveri še BSSID 2 in 3jega, čemur sledi še primerjava moči dokler ne dobimo samo ene vrstice, ki se ujema z našimi signali. V primeru, da je največje število ujemanj enako za več koordinat pokaže zadnjo točko v tabeli. V kolikor je level večji ali enak od prejšnjega povozi prejšnje vrednosti koordinat.

Ko dobimo vrnjene koordinate najverjetnejše lokacije tam prikažemo kurzor.


[[File:Screenshot 2013-06-10-22-54-12.png]]


'''7. ISKANJE POTI - PRIBLIŽEN ALGORITEM'''

Spravo je bilo mišljeno, da implementirava algoritem, ki bi narisal pot od naše trenutno lokacije do izbrane točke. Vendar, ko sva po analizi dela ugotovila koliko časa bi bilo potrebno vložiti, sva zaradi časovne stiske ta dela preskočila. Okvirna ideja algoritma je bila:
1. Dobimo točko kjer se trenutno nahajamo
2. Določimo kamor bi šli
3. Potegnemo črto na zemljevidu od začetka do konca in pogledamo katere vse prostore seka.
-Prostor lahko seka v 0,1 ali 2 točka.
-V kolikor seka v 2 točka, potem zagotovo gremo skozi prostor
-V kolikor seka v 1 točki, potem se samo dotikamo prostora
-V kolikor prostor sploh ne seka, potem nimamo nič s tem prostorom, prav gotovo v njemu pa ne moremo risati črtic.

V kolikor sekamo prostor v dveh točkah to pomeni, da gremo skozi neki prostor proti cilju, ker ne moremo hoditi naravnost skozi neki prostor temveč po hodnikih, potem pogledamo ploščino tega prostora. Skozi te dve točki potegnemo daljico in dobimo dve ploščini. Prvo vzamemo tisto, ki ima manjšo ploščino in je na tej strani hodnik zrišemo črt, v kolikor pa ne potem pa zrišemo na tisti strani prostora, kjer je večja ploščina seveda, ob pogoju da se tam nahaja hodnik.

V koliko pa dobimo eno točko potem ali smo na ciljni točka ali pa po postopku 2 točk določimo, ki je pot. Vse črte bi bile vnaprej narisane, algoritem bi samo postavil, da       so vidne in celotna črta (pot) bi morala biti zvezna.


'''8. KAR SMO DEJANSKO DOSEGLI'''

Dosegla sva vse razen iskanja poti. Se pa uporabniku na zemljevidu nariše ciljna točka, na kar s pomočjo zemljevida sam ugotovi pot.


'''9. KAR NISMO DOSEGLI'''

Nisva uspela implementirati algoritma, ki bi izrisal pot od naše trenutne lokacije pa do cilja, kamor smo namenjeni.


'''10. OMEJITVE'''

Omejila sva se na pritličje na FE, višjih nadstropij nisva upoštevala, ker je principi isti, s tem bi si pa samo zadala več mapiranja omrežij, medtem ko bi funkcionalnost aplikacije še vedno ista. Pri izdelavi zemljevida, sva se tudi omejila, tako da sva vsako točko na zemljevidu postavila tako, da je med točkama od 5 do 15 metrov razlike.
V kolikor bi uporabili zemljevid z višjo gostoto bi lahko prišlo do problemov. Saj je moč sprejema precej odvisna od naklona naprave, kje stojimo glede na dostopne točke in raznih drugih zunanjih vplivov.
Lociranje je boljše, če imamo na voljo več omrežij. Kar danes v razno raznih javnih ustanovah ni ravno problem. Vendar je v primeru dovolj velikih razlik še vedno možnost določiti lokacijo tudi v objektu z eno samo dostopno točko.
Prisotna omrežja naj bi vsak dan delovala in naj ne bi bilo večjih nihanja moči signalov.


'''11. PROBLEMI:'''

- samo skeniranje omrežij, ker je metoda veliko krat vrnila null
- nepravilno nastavljena vsa dovoljenja v manifest datoteki
- izris zaključne in končne točke, točke se je že izrisala ampak izklopila izris zemljevida


'''12. NAMEN APLIKACIJE'''

Določanje lastne lokacije in ciljnega prostora v zgradbi


'''13. PROFF OF CONCEPT:'''

Potrditev da se nahajamo v prostoru, katerega ugotovi na podlagi moči brezžični omrežij.


'''14. MOŽNOSTI ZA IZBOLJŠAVO'''

Namesto ročnega vnašanja omrežja, naredili algoritem, ki bi vsake tok časa preveril katera omrežja so na voljo, kakšne imajo moči.
V kolikor bi bilo kako novo omrežje bi ga aplikacija sama približno znala postaviti na zemljevid in bi znala ignorirati manjkajoče omrežje.
Adaptivno učenje, ko se uporabnik sprehaja po lokacij kjer še ni bil, bi s pomočjo računanja moči signalov (moč signala naj bi upadala s kvadratom razdalje) samo predvidelo lokacijo na prej znane meritve.

V kolikor bi se aplikacija uporabljala na stadionih in velikih dvoranah kjer so oštevilčeni sedeži, bi lahko podobno aplikacijo uporabili, da nas privede do našega sedeža.

V kombinaciji s 2. možnostjo za izboljšavo in NFC tehnologijo ali QR kodo, bi namesto da bi sedež ročno vpisovali v aplikacijo, kar s pomočjo NFC tehnologije ali QR kode dobili podatke z vstopnice ali ustreznega terminala na blagajni.

Uporaba aplikacije v vinski kleti, muzeju, trgovini... kjer bi aplikacija glede na trenutno pozicijo prikazala informacije o objektu, ki ga opazujemo (izdelku, sliki, kipi, zgodovino ipd.).


[[File:Augmented-reality.jpg]]



'''15. VIRI IN LITERATURA:'''

http://www.androidhive.info/2011/08/android-tab-layout-tutorial/

http://developer.android.com/reference/android/net/wifi/WifiManager.html#getScanResults()

http://developer.android.com/reference/android/net/wifi/WifiManager.html#startScanResults()

http://www.mkyong.com/android/android-alert-dialog-example/

http://android-er.blogspot.com/2011/01/monitor-wifi-status-and-information.html

http://android-er.blogspot.com/2011/01/detect-wifi-onoff-state.html

http://android-er.blogspot.com/2011/01/monitor-wifi-status-and-information.html

http://developer.android.com/training/basics/data-storage/databases.html

http://developer.android.com/reference/android/net/wifi/WifiManager.html

http://developer.android.com/reference/android/net/wifi/WifiManager.html#getScanResults()

http://stackoverflow.com/questions/5925420/how-to-create-a-string-from-string-array-or-arraylist

http://stackoverflow.com/questions/16760553/sending-more-data-and-messages-to-other-activity

http://thenewboston.org/list.php?cat=6