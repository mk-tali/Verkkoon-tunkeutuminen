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




## Lähteet  
Bianco. 2013. Enterprise Detection & Response. https://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html  
Caltagirone. 2013. The Diamond Model of Intrusion Analysis. https://www.threatintel.academy/wp-content/uploads/2020/07/diamond-model.pdf  
