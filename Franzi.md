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

      Gli indirizzi fisici riportati in un frame Ethernet sono sequenze di 48
      bit, nel caso che il frame sia destinato a tutti i dispositivi della rete esso è costituito da una sequenza di 48 bit impostati al valore _1_



















