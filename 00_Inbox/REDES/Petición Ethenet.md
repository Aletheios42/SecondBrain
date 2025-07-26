**MetaTags:** #_Todo
**Tags:** #Redes #Blockchain #ToLink 
- - -
```
Preámbulo: 10101010 10101010 ... (7 bytes)
SFD: 10101011

MAC Destino: FF:FF:FF:FF:FF:FF (broadcast)
MAC Origen: 00:1A:2B:3C:4D:5E (ejemplo de MAC origen)
EtherType: 0x0806 (indica que es ARP)

Payload (ARP request):
- Hardware type: 0x0001 (Ethernet)
- Protocol type: 0x0800 (IPv4)
- Hardware size: 06
- Protocol size: 04
- Opcode: 0x0001 (request)
- Sender MAC: 00:1A:2B:3C:4D:5E
- Sender IP: 192.168.1.5
- Target MAC: 00:00:00:00:00:00 
- Target IP: 192.168.1.10

FCS: [4 bytes de checksum]
```

- - - 
## ***Sources:***