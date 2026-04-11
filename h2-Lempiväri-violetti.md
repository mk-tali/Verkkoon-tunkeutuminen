# Lempiväri: violetti

## x) Lue ja vastaa lyhyesti kysymyksiin  
-Tuskan pyramidi  
Pyramidi näyttää millainen yhteys on indikaattorien, joita käytetään hyökkäyksen havaitsemiseen ja niiden käyttämisen estämisen aiheuttaman tuskan välillä.  
(Bianco 2013)  

-Timanttimalli  
Malli havannoi hyökkäyksen neljä pääosaa. Adversary, Capability, Infrastructure ja Victim.
(Caltagirone 2013)  

## a) Apache log  
Apache on jo asennettuna.  
<img width="523" height="146" alt="Näyttökuva 2026-04-10 145751" src="https://github.com/user-attachments/assets/415759bd-ce05-4826-945f-3d9536669e1b" />  
Ajoin komennon `sudo tail /var/log/apache2/access.log` ja menin netissä osoitteeseen http://localhost/. Tämän jälkeen tarkastelin terminaalia.  
<img width="1476" height="120" alt="Näyttökuva 2026-04-10 150159" src="https://github.com/user-attachments/assets/b584c93f-4ec2-46e7-8625-dc73c240b8c3" />  
Näistä ensimmäinen on omaa sivulataustani vastaava lokirivi. Järjestyksessä, asiakkaan ip-osoite, päivämäärä, HTTP-pyyntö, 200=tilakoodi, vastauksen koko ja User Agent eli selaimen ja käyttöympäristön tunnistetiedot.  

## b) Nmapped  
Ajoin komennon `sudo nmap -A -p 80 localhost` ja rajasin skannauksen vain porttiin 80.  
<img width="833" height="325" alt="image" src="https://github.com/user-attachments/assets/c0e39336-978c-43c1-bb4d-d201ce56a52d" />  
Nmap skannasi localhostilla portin 80/tcp, state = open, service = http, version Apache. Käyttöjärjestelmän tunnistus ei ole täysin luotettava, koska nmap tarvitsee vähintään yhden avoimen ja yhden suljetun portin.  

## c) Skriptit  
Nämä skriptit olivat automaattisesti päällä.  
<img width="449" height="35" alt="Näyttökuva 2026-04-10 152920" src="https://github.com/user-attachments/assets/172cdbce-d1ad-4216-9814-403581c8f3a6" />  

## d) Jäljet lokissa  
Ajoin komennon `sudo grep -i nmap /var/log/apache2/access.log`  
<img width="1443" height="450" alt="Näyttökuva 2026-04-10 153259" src="https://github.com/user-attachments/assets/95ecf606-cc33-42cb-b09e-0ae636cd664d" />
Nmap osumia löytyi helposti. Nmap User-Agent kohdassa näkyy Nmap Scripting Engine, eli pyynnöt tulivat Nmapin NSE-skripteiltä.  
Liian isosta lokista voi tunnistaa porttiskannauksen muun muassa tunnetuilla User-Agent sanoilla, suurella määrällä pyyntöjä tai 404 virheitä samalta ip-osoitteelta, sekä epätavallisilla http-metodeilla.  

## e) Wire sharking  
Aloitin kaappauksen Wiresharkissa loopback / lo liittymällä, koska skannaan localhost osoitetta. Ajoin komennon `sudo nmap -A -p 80 localhost`, pysäytin kaappakusen ja tallensin tiedoston .pcap muodossa. Etsin kohdat joissa on nmap hakusanalla 'frame contains "nmap"'.  
<img width="1209" height="575" alt="Näyttökuva 2026-04-10 155833" src="https://github.com/user-attachments/assets/e25d24c6-d994-4316-9981-a6e5745af48c" />  
Tässä näkyy, että source ja destination osoitteet ovat samat, protokolla on HTTP, pituus ja infossa erilaisia pyyntöjä.  

## f) Net grep
Ajoin komennot `sudo ngrep -d lo -i nmap` ja `sudo nmap -A -p 80 localhost`. <img width="1099" height="1188" alt="Näyttökuva 2026-04-10 161632" src="https://github.com/user-attachments/assets/9693b929-1e12-4324-9365-8701157623af" />  
<img width="1100" height="176" alt="Näyttökuva 2026-04-10 161710" src="https://github.com/user-attachments/assets/e963b7a3-e126-48ca-ac4c-4aac130d3427" />  

## g) Agentti  
Vaihdoin komennossa `sudo nmap -A -p 80 localhost` -A -p tilalle --script-args.    

## h) Pienemmät jäljet  
Ajoin uuden komennon `sudo nmap --script-args 80 localhost` ja nyt nmapista ei jäänyt jälkiä apache lokiin.  
<img width="1260" height="372" alt="image" src="https://github.com/user-attachments/assets/376c96f7-c747-4931-87c0-05f811122d05" />  

## i) Hieman vaikeampi: LoWeR ChEcK  
En ollut ihan varma, mitä tässä pitää tehdä. Edellisessä tehtävässäkään minulla ei näkynyt nmappia.  

## j) FCC ID  


## Lähteet  
Bianco. 2013. Enterprise Detection & Response. https://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html  
Caltagirone. 2013. The Diamond Model of Intrusion Analysis. https://www.threatintel.academy/wp-content/uploads/2020/07/diamond-model.pdf  
