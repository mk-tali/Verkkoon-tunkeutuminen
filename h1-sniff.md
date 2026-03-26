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
<img width="971" height="212" alt="image" src="https://github.com/user-attachments/assets/a5163661-e9fd-4b27-a201-2aefa0440aa5" />  
Sieppasin liikennettä ja kuvassa näkyy seuraavasti. `Linux cooked capture v1 = Network access layer`, `Internet Protocol version 4 = Internet layer`, `User Datagram Protocol = Transport layer`, `Domain Name System = Application layer.`


## Lähteet  
Karvinen 2025. Wireshark - Getting Started. https://terokarvinen.com/wireshark-getting-started/  
Karvinen 2025. Network Interface Names on Linux. https://terokarvinen.com/network-interface-linux/  
