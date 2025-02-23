# Project Work - Configurazione Rete Ufficio Marketing

## 📌 Descrizione
Questo progetto prevede la configurazione di una rete informatica per l'ufficio marketing di un'agenzia di viaggi. 
Sono stati configurati dispositivi di rete, VLAN, DHCP, access point e server, utilizzando **Cisco Packet Tracer** per la simulazione.

## 🛠️ Tecnologie e Strumenti Utilizzati
- **Cisco Packet Tracer** per la simulazione della rete
- **Configurazioni CLI (Command Line Interface)**
- **Router Cisco C1101-4P** e **Switch Cisco CBS250-24T**
- **Rete cablata con cavi UTP Cat6**
- **NAS per backup e archiviazione dati**

## 🔧 Configurazioni di Rete

### VLAN Configurate
| VLAN  | Nome       | Rete                | Subnet Mask          |
|-------|-----------|---------------------|----------------------|
| 30    | Marketing | 192.168.30.0/26     | 255.255.255.192     |
| 40    | Wireless  | 192.168.40.0/26     | 255.255.255.192     |
| 50    | Server    | 192.168.50.0/26     | 255.255.255.192     |
| 60    | Management | 192.168.60.0/26    | 255.255.255.192     |

### Configurazione del Router (Router on Stick)
```bash
enable
conf t
int g0/1.30
encapsulation dot1Q 30
ip address 192.168.30.62 255.255.255.192
int g0/1.40
encapsulation dot1Q 40
ip address 192.168.40.62 255.255.255.192
int g0/1.50
encapsulation dot1Q 50
ip address 192.168.50.62 255.255.255.192
int g0/1.60
encapsulation dot1Q 60
ip address 192.168.60.62 255.255.255.192
end
```

### Configurazione VLAN sullo Switch
```bash
enable
conf t
interface range fa0/2-6
switchport mode access
switchport access vlan 30
no shutdown
interface g0/1
switchport mode trunk
end
```

## 📷 Schema della Rete
Ecco la topologia della rete configurata in **Cisco Packet Tracer**:

![Network Topology](Diagrams/network_topology.jpg)

## 📂 Contenuti del Repository
- `Documentation/` → Relazione tecnica dettagliata
- `Configs/` → File con le configurazioni CLI di router e switch
- `Diagrams/` → Diagramma della rete e schemi VLAN
- `PacketTracer/` → File `.pkt` della simulazione

## 📜 Autore
📌 **Barbara Ferrero**  
🔗 [LinkedIn](https://www.linkedin.com/in/barbara-ferrero)
