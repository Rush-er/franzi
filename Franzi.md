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


__Livello__

__7__ Applicazione            
__6__ Presentazione
__5__ Sessione

      HTTP (Hyper-Text Transfer Protocol )
      SMTP (Simple Mail Transfer Protocol )
      POP (Post Office Protocol )
      FTP (File Transfer Protocol )
               

  
__4__ Trasporto 
            
      TCP (Transmission Control Protocol )
      UDP (User Datagram Protocol )
__3__ Rete 

      IP (Internet Protocol )
__2__ Data-link 

      IEEE-802.3 (wired Ethernet )
      IEEE-802.11 (wireless Ethernet )
      PPP (Point-to-Point Protocol )
      HDLC (High-level Data-Link Control )
