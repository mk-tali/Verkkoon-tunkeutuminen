# h1 Sniff  

## x) Tiivistelmät  
Wireshark - Getting Started  
-Ohjeet Wiresharkin asentamiselle Linuxille.  
-Lisätään itsemme ryhmään, jotta voi sniffata.  
-Jos liikennettä ei näy, koita surffata nettiä.  
-Tulokset voi tallentaa ja suodattaa.  
(Karvinen 2025. Wireshark - Getting Started)  

Network Interface Names on Linux  
-Network interface on kuin network card, mutta ei fyysinen.  
-Artikkeli kertoo mitä nimet tarkoittavat.  
-Nimen alku, prefix, määrittelee tyypin.
(Karvinen 2025. Network Interface Names on Linux)

## a) Linux  
Linux on jo asennettuna  

## b) Ei voi kalastaa  
Täältä pystyn katkaisemaan yhteyden nettiin. 
<img width="418" height="282" alt="image" src="https://github.com/user-attachments/assets/7eb1f24b-455f-4125-8dc3-f882735bbec7" />  

## c) Wireshark  
Wireshark on valmiiksi asennettuna Kalissa.  
<img width="806" height="608" alt="image" src="https://github.com/user-attachments/assets/8ab06028-d843-4c6e-b932-b9558ff79c07" /> 

## d) Oikeesti TCP/IP  
Sieppasin liikennettä ja kuvassa näkyy seuraavasti.  
`Linux cooked capture v1 = Network access layer,`  
`Internet Protocol version 4 = Internet layer,`  
`User Datagram Protocol = Transport layer`  
`Domain Name System = Application layer.`  
<img width="973" height="194" alt="image" src="https://github.com/user-attachments/assets/bfd06919-05bd-4547-a6e0-6a63529a34f3" />  

## e) Mitäs tuli surffattua?    
Protokollista löytyy ARP, DNS, QUIC, TCP ja TLS. Kaappaus kesti 7,5 sekuntia. 2 ethernet laitetta ja 7 IPv4 laitetta, yli tuhat pakettia.  

## g) Käyttäjän verkkokortti  
Yritin selvittää verkkokortin merkkiä täältä, mutta osoitteelle vastaavaa ei löytynyt.  
<img width="594" height="476" alt="image" src="https://github.com/user-attachments/assets/a1b19797-3e90-4296-a285-2abb9a1be025" />  
Uskon, että se johtuu tästä.  
<img width="1013" height="71" alt="image" src="https://github.com/user-attachments/assets/aa887500-f4fb-4c92-9174-55d03fc4d2f6" />  

## h) Weppipalvelimet  
Tutkin annettua tiedostoa ja heti alussa huomasin, että oli menty googlen kautta terokarvinen.com. Myös terokarvinen.goatcounter.com.  

## i) Analyysi.  
Tätä analyysia varten menin firefoxissa githubiin.  
Ensin kone teki ARP kyselyn.  
<img width="1024" height="55" alt="image" src="https://github.com/user-attachments/assets/3d1c38cc-6f78-485b-bde9-f6adbf2b423b" />  
DNS mozillaan.
<img width="1587" height="42" alt="image" src="https://github.com/user-attachments/assets/fb3b6349-178a-4ccb-993e-c3f9ffa9eadf" />  
DNS githubiin.  
<img width="1535" height="181" alt="image" src="https://github.com/user-attachments/assets/c997e2cf-415e-4b21-b7d9-3d74e48cde55" />  
DNS githubiin käyttäjälleni a



## Lähteet  
Karvinen 2025. Wireshark - Getting Started. https://terokarvinen.com/wireshark-getting-started/  
Karvinen 2025. Network Interface Names on Linux. https://terokarvinen.com/network-interface-linux/  
