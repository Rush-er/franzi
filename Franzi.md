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
__Trasmissione inaffidabile__ dei dati (datagram) viene impiegato in situazioni in cui la perdita di pacchetti, o l’arrivo al destinatario in ordine diverso da quello di trasmissione, non costituisce un problema.

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

#### Header 
![N|Solid](https://imgur.com/fnFKqYZ.png)


|  Campi | Descrizione  |
|:-:|:--|
|  Versione | È la versione del protocollo IP|
| Priorità e tipo di servizio  |  Usato per evidenziare i pacchetti che hanno alta priorità di trasmissione |
|  Lunghezza totale |  È la dimensione in byte del pacchetto |
|  TTL (Time To Live) | Questo valore viene decrementato ogni volta che il pacchetto viene instradato da un router |
| Protocollo  | Usato per identificare il protocollo del livello di trasporto  |
| Indirizzo IP sorgente  | Sorgente  |
| Indirizzo IP destinazione  |  Destinazione |


__DNS__ (Domain Name System),  in grado di restituire l' indirizzo IP associato ad un URL


## Porte
__16__ bit (valori compresi tra 0 e 65535) che identifica univocamente la sorgente o la destinazione dei segmenti di dati nel contesto di un dispositivo.

__Well-known port number__
|  Protocollo applicativo | Numero di porta  |
|:-:|:--|
| __FTP__ (File Transfer Protocol )  | 20, 21 |
|  __SMTP__ (Simple Mail Transfer Protocol) | 25  |
|  __DNS__ (Domain Name Server ) |  53 |
|  __HTTP__ (Hyper-text Transfer Protocol ) |  80 |
|  __POP__ (Post Office Protocol ) |  110 |
|  __NTP__ (Network Time Protocol ) | 123  |
|  __HTTPS__ (Hyper-text Transfer Protocol Secure) |  443 |
|  __Doom__ (videogame) | 666 |
| __FTPS__ (File Transfer Protocol Secure)  |  989, 990 |

I numeri di porta di valore compreso tra __0__ e __1023__ sono riservati per __protocolli standard__


#### Intestazioni

- __UDP__

   ![N|Solid](https://imgur.com/0JxzhmA.png)
   
| Campi  | Descrizione  |
|:-:|:--|
| __Porta sorgente__  |  Numero porta del mittente |
|  __Porta destinazione__ | Numero porta del destinatario  |
|  __Lunghezza__ | È la dimensione in byte del pacchetto.  |
|  __Checksum__ |  Codice calcolato a partire dal contenuto del segmento di dati con un algoritmo predefinito; viene ricalcolato dal dispositivo destinatario per verificare che i dati ricevuti sono corretti |

- __TCP__

   ![N|Solid](https://imgur.com/EEVIEgi.png)

| Campi  | Descrizione  |
|:-:|:--|
| __Porta sorgente__  |  Numero porta del mittente |
|  __Porta destinazione__ | Numero porta del destinatario  |
|  __Sequence number__  | È il numero di byte inviati dall’inizio della connessione.
|  __Acknowledgement number__ |   numero di byte inviati dall’inizio della connessione.
|  __Checksum__ |  Codice calcolato a partire dal contenuto del segmento di dati con un algoritmo predefinito; viene ricalcolato dal dispositivo destinatario per verificare che i dati ricevuti sono corretti |

    I campi Sequence number e Acknowledgement number sono utilizzati per verificare, ed eventualmente correggere mediante ritrasmissione di parti mancanti, l’integrità del flusso di dati.

## Il modello client/server e il protocollo applicativo HTTP: dal web al cloud

#### HTTP

__Metodi__

|     Metodo     |                                     Operazione                                    |
|:-----------:|:---------------------------------------------------------------------------------------------------------------------------------------|
| __GET__     | Richiede al server la risorsa identificata dall’URL specificato.                
| __HEAD__    | Come GET, ma la risposta fornita dal server non comprende la risorsa. |
| __POST__    | Integra la risorsa identificata dall’URL specificato con le informazioni in- viate.                                                     |
| __PUT__     | Crea o aggiorna la risorsa identificata dall’URL specificato a partire dalle informazioni inviate.                                      |
| __DELETE__  | Elimina la risorsa identificata dall’URL specificato                                                                                    |
| __TRACE__   | Richiede al server una risposta costituita dalle informazioni inviate («eco»).                                                          |
| __CONNECT__ | Richiede al server un accesso diretto al protocollo TCP.                                                                                |
| __OPTIONS__ | Richiede al server l’elenco dei metodi accettati per la risorsa identificata dal l’URL specificato.                                     |

__Risposte richieste HTTP__

| Formato del codice di stato | Categoria                                                                                                                                                 |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
|     1XX (100, 101, ...)     |                                                 Informativa (codici di negoziazione tra client e server).                                                 |
| 2XX (200, 201, ...)         | Successo (codici che confermano al client che la richiesta avan- zata al server è stata eseguita correttamente).                                          |
| 3XX (300, 301, ...)         | Ridirezione (codici che comunicano al client che la richiesta avanzata al server NON è stata eseguita a causa di un’errata specificazione della risorsa). |
| 4XX (400, 401, ...)         | Errore del client (codici che comunicano al client che la richiesta avanzata al server NON è stata eseguita perché errata).                               |
| 5XX (500, 501, ...)         | Errore del server (codici che comunicano al client che la richiesta avanzata al server NON è stata eseguita a causa di un errore del server).             |

__Multipurpose Internet Mail Extension__ (MIME)
Standard di Internet che estende la definizione del formato dei messaggi di posta elettronica, originariamente definito dall'SMTP, il protocollo di trasmissione delle email



