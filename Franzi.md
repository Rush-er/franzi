# Tecnologie e Progettazione di sistemi informatici _aka_ __Franzi__

[![N|Solid](https://imgur.com/h5A9ZdX.png)](https://t.me/materiale5/33)

##### Internet è un sistema di informazioni globale che:

   - è __logicamente interconnesso__ da uno spazio di indirizzamento unico e globale basato sul __protocollo IP__ (_Internet Protocol_) o le sue successive estensioni o sviluppi;
   
   - è in grado di __supportare la comunicazione__ tramite la suite di __protocolli TCP/IP__ (_Transmission Control Protocol e Internet Protocol_) o le sue successive estensioni o sviluppi e/o altri protocolli compatibilicon IP;
   
   - __fornisce, utilizza o rende accessibili__, sia pubblicamente sia privatamente, __servizi di  comunicazione__ di alto livello stratificati e basatisulla correlata infrastruttura qui descritta.


# Reti

###### Rete  locale  (LAN) / Reti locali wireless (WLAN)
![N|Solid](https://imgur.com/Db60kCEl.png)

###### Rete geografica (WAN) Internet
![N|Solid](https://imgur.com/WPTPgiBl.png)



## La tecnologia __packet-switching__
La tecnologia __packet-switching__  è  alla  base  del  funzionamento  di  tutte  le  reti  di  telecomunicazione  moderne; un  messaggio  trasmesso  da  un dispositivo mittente  a  un  dispositivo  destinatario  sia  suddiviso  in  __pacchetti__  di  piccole  dimensioni:  ogni  singolo  pacchetto  include l’__indirizzo__ sia del dispositivo ___mittente___ sia del dispositivo ___destinatario___.

__Robusta__ rispetto ai guasti e ai malfunzionamenti degli apparati e dei collegamenti che costituiscono una rete di computer. 
__Risolvere__  automaticamente  il  problema ricorrente della ___congestione del traffico___.

## Lo standard __Ethernet__
##### __Due tipi:__
 - __wired__ (_cablata_): utilizzano ___cavi in rame___ o ___fibre ottiche___, varia in funzione delle caratteristiche dei cavi e degli apparati di rete.
 
- __wireless__ (_senza fili_): utilizzano le ___onde radio___ nelle bande di frequenza  comprese  tra  
  
    - 2,4  e  2,5  GHz  
    - 5,7  e  5,9  GHz;  

   La _velocità_ di trasmissione e la _distanza_ raggiungibile dipendono dalle caratteristiche dei dispositivi e degli apparati di rete.

##### __Frame__


| Preambolo  | SOF  | Destinazione  | Mittente  | Lunghezza Dati  |  Dati | FCS  |
|---|---|---|---|---|---|---|
| 7 byte  | 1 byte  | 6 byte  | 6 byte  | 2 byte  | 46-1500 byte  |  4 byte |

- Primi __8__ byte &rarr; _sincronizzare il dispositivo che riceve_.
- ultimi __4__ byte &rarr; _verificare la correttezza dei dati ricevuti rispetto a quelli trasmessi_.

   Gli indirizzi fisici riportati in un frame Ethernet sono sequenze di 48 bit, nel caso che il frame sia destinato a tutti i dispositivi della rete esso è costituito da una sequenza di 48 bit impostati al valore _1_


__CSMA-CD__ (_Carrier Sense Multiple Access-Collision Detection_)

1. Un dispositivo prima di trasmettere un frame verifica che non vi siano trasmissioni già in corso.

2. Se il collegamento risulta disponibile, il dispositivo inizia la trasmissione del frame, la trasmissione viene monitorata allo scopo di rilevare una possibile collisione se presenti più dispositivi.

3. Nel caso che sia rilevata una collisione, il dispositivo interrompe la trasmissione e attende un tempo di durata casuale prima di ritentare una
nuova trasmissione del frame.

4. Dopo tre tentativi di trasmissione che si risolvono in una collisione la trasmissione del frame non viene più ritentata ed è considerata fallita.


## Il modello __ISO__/__OSI__ e lo stack di protocolli __TCP__/__IP__

| Livello | Funzione  |
|---|---|
| __7__ Applicazione  | Comunicazione dati tra i processi in esecuzione su due computer della rete  |
|  __6__ Presentazione| Rappresentazione dei dati in un formato comune tra i processi in esecuzione su due computer della rete  |
|  __5__ Sessione |  Gestione della sessione di comunicazione tra i processi in esecuzione su due computer della rete |
| __4__ Trasporto  |  Trasferimento dei ___segmenti___ tra i processi in esecuzione su due computer della rete,  comunicazione affidabile gestendo gli errori del livello di rete |
|  __3__ Rete | Trasferimento dei pacchetti attraverso la rete, dal computer di origine fino al computer di destinazione;trasmissione non affidabile |
| __2__ Data-link  |  Trasmissione/ricezione di un ___frame___ tra due dispositivi direttamente connessi |
|  __1__ Fisico |  Trasmissione/ricezione dei segnali elettrici, ottici o a radiofrequenza che rappresentano i singoli bit|


##### __Livello__

- __7__ Applicazione                  
- __6__ Presentazione
- __5__ Sessione

      Protocollo
      - HTTP (Hyper-Text Transfer Protocol )
      - SMTP (Simple Mail Transfer Protocol )
      - POP (Post Office Protocol )
      - FTP (File Transfer Protocol )
               

  
- __4__ Trasporto 
       
      Protocollo     
      - TCP (Transmission Control Protocol )
      - UDP (User Datagram Protocol )
- __3__ Rete 

      Protocollo
      - IP (Internet Protocol )
      
- __2__ Data-link 

      Protocollo
      - IEEE-802.3 (wired Ethernet )
      - IEEE-802.11 (wireless Ethernet )
      - PPP (Point-to-Point Protocol )
      - HDLC (High-level Data-Link Control )
      
      
  
      
 __Trasporto__
 - __TPC__
__Creazione__ della connessione virtuale tra i due computer che partecipano alla comunicazione.
__Rilevazione__ di eventuali ___pacchetti___ ricevuti _fuori ordine_ o _andati persi_. 
La gestione di queste situazioni realizza una trasmissione dei dati __affidabile priva di errori__.

- __UDP__
__Trasmissione inaffidabile__ dei dati e viene impiegato in situazioni in cui la perdita di pacchetti, o l’arrivo al destinatario in ordine diverso da quello di trasmissione, non costituisce un problema.

__Rete__
- __IP__
   Trasferimento dei pacchetti attraverso la rete, dal computer di origine fino al computer di destinazione; a questo livello la trasmissione dei dati è __inaffidabile__. Ogni dispositivo e apparato è univoco. Due versioni: v. 4 v. 6. 
Possono essere impiegate contemporaneamente sulla stessa rete LANG WAN.

#### Incapsulazione
Il funzionamento __congiunto__ di più protocolli a vari livelli gerarchici è
basato sulla tecnica di ___incapsulazione___ dei singoli pacchetti costituiti ai
livelli più alti del modello nei pacchetti dei livelli più bassi come dati.

- __Applicazione__ &rarr; i dati sono frazionati e ogni frazione viene trasmessa invocando il protocollo TCP
-  __Trasporto__ &rarr; il protocollo TCP aggiunge la propria intestazione configurando un segmento che trasmette invocando il protocollo IP
- __Rete__ &rarr; il protocollo IP aggiunge la propria intestazione configurando un pacchetto che trasmette invocando il protocollo del livello
data-link
- Trattandosi di una rete LAN al pacchetto IP viene aggiunta l’intestazione del frame Ethernet (e in questo caso anche, in coda prima della modulazione effettiva dei singoli bit sul mezzo fisico di trasmissione.

![N|Solid](https://imgur.com/12hKxB9.png)


## Protocollo IP
Il protocollo IP ha il compito di __trasferire__ un pacchetto dal computer _mittente_ al computer _destinatario_: a questo scopo ogni computer presente sulla stessa rete deve disporre di un indirizzo IP univoco.

#### IPv4

__32__ bit suddiviso in due parti:
- l’indirizzo che identifica la __rete__ a cui appartiene il dispositivo. __Netmask__


- l’indirizzo del __dispositivo__ all’interno della rete


__ARP__ (Address Resolution Protocol), che inoltra in broadcast a tutti i dispositivi della rete LAN una
richiesta contenente l’indirizzo IP da risolvere;

La configurazione di un computer o di un dispositivo connesso a una rete LAN o WAN deve di conseguenza prevedere i tre seguenti parametri:
- indirizzo IP
- network
- indirizzo IP del gateway

