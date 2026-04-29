# WiFi  
## a) Tutustu wifi challenge lab 2.1 harjoitus ympäristöön ja käytä tarvittaessa hyväksesi jo olemassa olevia ohjeita.  
Tein tehtävät Recon 1-4 ja OPN 5. Recon 3 tehtävässä en saanut sivuston mukaan oikeaa vastausta, vaikka seurasin ohjeita. Sain vastaukseksi wifi-offices,Jason.

## b) Kirjoita raportti siitä mitä opit ja mitkä asia yllättivät sinut kun tutustuit harjoitukseen.  
Harjoituksiin tutustuessa opin yksinkertaisia komentoja ja tapoja millä kuunnella ja murtautua WiFi verkkoihin.  
Opin hyökkäyksiin liittyvät vaiheet, Tiedustelu, Hyökkäys ja Tunkeutuminen. Ensin aloitetaan wlanien monitorointi komennolla `airmon-ng start "wlan"`.  
<img width="834" height="512" alt="image" src="https://github.com/user-attachments/assets/0da293c7-f9db-4de3-b80b-5780fceaec68" />  

Sen jälkeen kuunnellaan mitä wlan verkkoja löydämme komennolla `airodump-ng "wlan"`.  
<img width="1026" height="753" alt="image" src="https://github.com/user-attachments/assets/eb611836-2553-464f-8f43-98859e6151c8" />  

Komennolla `aireplay-ng` generoidaan liikennettä verkkoon.  
<img width="742" height="296" alt="image" src="https://github.com/user-attachments/assets/16a997ff-5967-47e0-9947-12055091bb92" />  

Lopuksi hyökätään tallennettuun tiedostoon komennolla `aircrack-ng` 
Recon 4 tehtävässä hyökättiin rockyou.txt tiedoston avulla, mutta ilman `aircrack-ng` komentoa, vaan käytettiin mdk4 löytämään oikea ESSID.  
<img width="851" height="192" alt="image" src="https://github.com/user-attachments/assets/d63a4b7e-c2cc-44c1-8a16-c90f4b73d9fa" />  

OPN 5 tehtävässä luotiin free.conf tiedosto, jonka avulla voitiin yhdistää verkkoon käyttämällä komentoa `wpa_supplicant -Dnl80211 -iwlan2 -c free.conf` kun toisessa terminaalissa ajettiin komento `dhclient wlan2 -v` saatiin ip osoite, jossa pääsin kirjautumaan adminina.

Se mikä minut yllätti, kun tein harjoituksia oli se, että kuinka yksinkertaista wlan verkkoihin tunkeutuminen loppujen lopuksi oli.

## c) Miten suhtautumisesi WLanin turvallisuuteen muuttui sen jälkeen kun teit harjoitukset?  
Tajusin, että yksityisetkään Wlanit ei olekkaan niin turvallisia, kuin olin ajatellut. 
 
