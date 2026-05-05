# h7 Aaltoja harjaamassa  

## x) Tiivistelmät  
Universal Radio Hacker SDR Tutorial on 433 MHz radio plugs  
-Käytetään Spectrum Analyzeria tarkistamaan onko taajuus oikein.  
-Jos valitaan ihan keskikohta, sdr:ssä on jokin juttu, joka estää sen samplaamisen.  
-Tallennetaan lähetys valitulla taajuudella.  
-Tarkistetaan, että bitit ovat oikein.  
-Signaali voidaan näyttää bitteinä, hexana tai ASCII muodossa.  
(Hubacek. 2019.)

Decode 433.92 MHz weather station data  
-433 MHz toimivat laitteet voidaan decodata käyttämällä rtl_433.  
-rtl_433 näyttää paljon hyödyllistä tietoa laitteista.  
-URH:n avulla voidaan tallentaa ja analysoida signaaleja.  
-Tallennettuja signaaleja voidaan tutkia bitteinä.  
(Cornelius. 2022.)  

## a) Lähteet ja läppä
Tehty.  

## b) rtl_433  
rtl_433 on asennettu ja toimii.  
<img width="583" height="67" alt="image" src="https://github.com/user-attachments/assets/df055cf4-82ff-48b2-bc22-7da459d13766" />  

## c) Automaattinen analyysi  
Latasin tiedoston ja analysoin sen rtl_433 avulla.  
<img width="955" height="844" alt="image" src="https://github.com/user-attachments/assets/1b3b44d9-d08c-44fb-8293-48d4f470125d" />  
Tiedostosta löytyy laitteiden nimiä, klikaanklikuit-switch, Proove-security ja Nexa-Security. House Code ja id ovat samat 8785315. Command: Off. Unit: 3. Channel 3. Ja muuta tietoa.  

## d) Too complex 16?  
Muutin complex16s tiedoston rtl_433 sopivaksi vaihtamalla tiedoston nimen komennolla `cp "Recorded-HackRF-20250411_183354-433_92MHz-2MSps-2MHz.complex16s" \ "hackrf_433.92M_2000k.cs8"`  
<img width="973" height="910" alt="image" src="https://github.com/user-attachments/assets/4db95af5-81a8-41c0-b06b-7778909a4180" />  
Sain avattua tiedoston rtl_433:lla ja se näytti samalta tiedostolta kuin aiemmassa tehtävässä.  

## e) Ultimate  
Asensin URH:n  
<img width="1264" height="468" alt="image" src="https://github.com/user-attachments/assets/c8942c7c-5e40-4f02-813d-98d91737fa89" />  
Suljin ja avasin terminaalin. Sitten ajoin komennon urh ja graafinen käyttöliittymä aukesi. Avasin tiedoston URH:lla ja tarkastelin tiedostoa.  
<img width="2557" height="807" alt="image" src="https://github.com/user-attachments/assets/5c950dfa-542f-4e35-8007-7ba1b6402176" />  

## f) Yleiskuva  
Näyte on 5.49s pitkä, 

## Lähteet  
Cornelius. 2022. Decode 433.92 MHz weather station data. https://www.onetransistor.eu/2022/01/decode-433mhz-ask-signal.html  
Hubacek. 2019. Universal Radio Hacker SDR Tutorial on 433 MHz radio plugs. https://youtu.be/sbqMqb6FVMY?t=199  
Karvinen Tero. Verkkoon tunkeutuminen ja tiedustelu. https://terokarvinen.com/verkkoon-tunkeutuminen-ja-tiedustelu/  
