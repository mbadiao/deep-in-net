# ✅Deep-in-Net: Network Architecture Simulation

## 📚 Présentation
Ce projet illustre la simulation de plusieurs topologies de réseau à l'aide de Cisco Packet Tracer. L'objectif est d'explorer le sous-réseautage, l'adressage IP, les principes de base de la commutation et du routage, ainsi que la conception de réseaux à l'aide de commutateurs et de concentrateurs.


### 1. Topologies point à point
3 connexions point à point distinctes

Chaque connexion comprend deux PC connectés via Ethernet

#### Exemple d'adresses IP :

192.168.1.3/24 (pc0) --> 192.168.1.4/24 (pc1)

192.168.13.82/29 (pc2) --> 192.168.13.83/29 (pc3)

192.168.13.254/29 (pc4) --> 192.168.13.253/29 (pc5)

🔧 Tâches réalisées :
Assignation d'adresses IP statiques

Validation du sous-réseau

Test ping entre les appareils

## 🚀 Étapes pour recréer le projet (ex01.pkt)
Ouvrez Cisco Packet Tracer

Créez les topologies :
Utilisez « Terminaux » > « PC-PT » pour les PC

Connectez les périphériques à l'aide des câbles appropriés :

PC ↔ PC : Câble croisé

Attribuez les adresses IP manuellement on click sous « PC > Bureau > Configuration IP »

Utilisez l'invite de commande pour tester la connectivité avec une commande ping

## 2. Topologies LAN
#### 🟦 LAN basé sur un commutateur
5 PC connectés à un commutateur

Sous-réseau : 192.168.1.0/29

#### 🟩 LAN basé sur un concentrateur
5 PC connectés à un concentrateur

Sous-réseau : 192.168.1.193/27

#### 🔧 Tâches effectuées :
Configuration IP pour tous les clients (comme dans ex01.pkt)

Connexion via des câbles appropriés (directs)


Test de connectivité par ping

### 📐 Résumé du sous-réseau
Préfixe de sous-réseau Hôtes Plage Appareils utilisés : <br />
192.168.1.0 /24 192.168.1.1 – 192.168.1.254 2 PC <br />
192.168.1.192 /27 192.168.1.193 – 192.168.1.222 5 PC

## 🚀 Étapes pour recréer le projet (ex02.pkt)
Ouvrez Cisco Packet Tracer

Créez les topologies :

Utilisez « End devices » > « PC-PT » pour les PC 

Utilisez « Network devices » > « switches »  pour les switch 2960

Utilisez « Network devices » > « Hubs »  pour le PT-Hub

PC ↔ Commutateur/Concentrateur : Câble droit

Attribuez les adresses IP manuellement on click sous « PC > Bureau > Configuration IP »

lan 1 (switch)

pc0 192.168.1.1/29 <br>
pc1 192.168.1.2/29 <br>
pc2 192.168.1.3/29 <br>
pc3 192.168.1.4/29 <br>
pc4 192.168.1.5/29 <br>

lan 2 (hub)

pc5 192.168.1.193/27 <br>
pc6 192.168.1.194/27 <br>
pc7 192.168.1.195/27 <br>
pc8 192.168.1.196/27 <br>
pc9 192.168.1.197/27 <br>


## 3 🌐 Topologies Serveurs et Réseau centralisé
Cette partie du projet simule un réseau d'entreprise avec un rack de serveurs, connecté à plusieurs postes clients via un commutateur (switch).

# 🖥️ Disposition des équipements
## 🗄️ Serveurs (dans le rack)
HTTPS Server – IP : 192.168.1.99

FTP Server – IP : 192.168.1.100

DNS Server – IP : 192.168.1.101

DHCP Server – 192.168.1.102 (attribue dynamiquement)

## 💻 Clients (PC0 → PC5)
Connectés via le Switch 2950

Exemple d’adresse statique attribuée : 192.168.1.7/24

## 🔧 Tâches effectuées
Configuration statique des serveurs

Configuration dynamique (DHCP) ou statique des PC selon le scénario

Connexions via câbles directs (straight-through)

Tests de connectivité via ping

Configuration DNS (selon le scénario)

Test d'accès aux services :

FTP (ftp://192.168.1.100)

HTTPS (https://192.168.1.99)

DNS (https://192.168.1.101)

DHCP (https://192.168.1.102)

Résolution DNS (avec le serveur 192.168.1.101)

## 📐 Adressage IP utilisé
Appareil	Adresse IP	Rôle
HTTPS Server	192.168.1.99	Serveur web sécurisé <br>
FTP Server	192.168.1.100	Transfert de fichiers <br>
DNS Server	192.168.1.101	Résolution de noms <br>
DHCP Server	192.168.1.102	Attribution d’adresses <br>
PC0 → PC5	192.168.1.X/24	Postes clients

## ℹ️ Le masque utilisé est /24, permettant jusqu’à 254 hôtes valides.

## 🚀 Étapes pour recréer ce scénario (ex03.pkt)
Ouvrez Cisco Packet Tracer

Placez :

4 serveurs (Server-PT) depuis End Devices

6 PC (PC-PT)

1 switch (2960)

Connectez tous les équipements via des câbles directs

Configurez :

Les serveurs avec des IP statiques

Les PC avec IP statique ou DHCP (selon configuration)

Configurez les services sur chaque serveur (via Services dans le menu des serveurs)

Testez les services depuis les clients :

Pings

FTP/HTTPS

Résolution DNS

# 4 .🔁  Topologies de Routage Point-à-Point avec Routeur

Ce scénario illustre un exemple simple de routage entre deux réseaux à l’aide d’un routeur Cisco 1841, avec deux PC sur des sous-réseaux séparés.

---

## 🖥️ Équipements et Adressage

| Équipement | Type     | Adresse IP        | Masque           | Rôle                     |
|------------|----------|-------------------|------------------|--------------------------|
| PC0        | PC-PT    | 192.168.1.2       | 255.255.255.252  | Hôte dans sous-réseau 1 |
| PC1        | PC-PT    | 192.168.2.2       | 255.255.255.252  | Hôte dans sous-réseau 2 |
| Routeur    | 1841     | - Interfaces IP à configurer - | - | Pont entre les deux réseaux |

---

## 📐 Détails IP

- **PC0** → réseau `192.168.1.0/30`
  - IP : `192.168.1.2`
  - Masque : `255.255.255.252`
  - Passerelle : ex. `192.168.1.1`

- **PC1** → réseau `192.168.2.0/30`
  - IP : `192.168.2.2`
  - Masque : `255.255.255.252`
  - Passerelle : ex. `192.168.2.1`

---

## ⚙️ Étapes de configuration

1. **Configurer les interfaces du routeur :**

   ```bash
   Router> enable
   Router# configure terminal

   # Interface vers PC0
   Router(config)# interface fastethernet0/0
   Router(config-if)# ip address 192.168.1.1 255.255.255.252
   Router(config-if)# no shutdown

   # Interface vers PC1
   Router(config)# interface fastethernet0/1
   Router(config-if)# ip address 192.168.2.1 255.255.255.252
   Router(config-if)# no shutdown

2. **Configurer les passerelles sur les PC** :

PC0 : Gateway → 192.168.1.1

PC1 : Gateway → 192.168.2.1

3. **Tester la connectivité** :

Depuis PC0 : ping 192.168.2.2

Depuis PC1 : ping 192.168.1.2


# 5 🧭 Toplogie Routage Inter-VLAN avec Sous-Réseaux Distincts

Ce scénario représente une infrastructure réseau segmentée en deux sous-réseaux distincts, interconnectés via un **routeur central (Cisco 2911)**. Chaque sous-réseau est relié à un switch, avec plusieurs hôtes (PC-PT) dans chaque segment.

---

## 🧩 Structure du Réseau

### 🔀 Routeur
- **Modèle :** Cisco 2911
- **Rôle :** Interconnexion des sous-réseaux (routage)

### 🔁 Switchs
- 2 Switchs (Switch0 et Switch1) pour chaque sous-réseau

---

## 🌐 Sous-réseaux & Adressage IP

### 🧱 Sous-Réseau A
- **Adresse réseau :** `192.168.1.0/29`
- **Plage IP utilisable :** `192.168.1.1 – 192.168.1.6`
- **Passerelle (routeur) :** `192.168.1.1` (interface vers Switch0)
- **Hôtes connectés :** PC0 à PC4

### 🧱 Sous-Réseau B
- **Adresse réseau :** `192.168.1.192/27`
- **Plage IP utilisable :** `192.168.1.193 – 192.168.1.222`
- **Passerelle (routeur) :** `192.168.1.193` (interface vers Switch1)
- **Hôtes connectés :** PC5 à PC9

---

## 🖥️ Tableau des Appareils

| Appareil | Type   | IP Adresse          | Sous-Réseau        |
|----------|--------|---------------------|--------------------|
| PC1-5    | PC-PT  | 192.168.1.2 à .6    | 192.168.1.0/29     |
| PC6-10   | PC-PT  | 192.168.1.194 .198      | 192.168.1.192/27   |
| Router0  | Cisco 2911 | 192.168.1.1 / .193 | Interfaces Fa0/0, Fa0/1 |
| Switch0  | Switch | ---                 | Connecté à PC0-4   |
| Switch1  | Switch | ---                 | Connecté à PC4-9  |

---

## ⚙️ Étapes de Configuration

### 1. Interfaces du Routeur
```bash
Router> enable
Router# configure terminal

# Interface vers Sous-Réseau A
Router(config)# interface fastethernet0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.248
Router(config-if)# no shutdown

# Interface vers Sous-Réseau B
Router(config)# interface fastethernet0/1
Router(config-if)# ip address 192.168.1.193 255.255.255.224
Router(config-if)# no shutdown
```


# 6 🌐 Topologie Routage entre deux LAN via deux routeurs

Ce scénario représente deux réseaux locaux (LAN) connectés via un lien point-à-point entre deux routeurs. Chaque LAN contient un PC configuré avec une adresse IP statique.

---

## 📌 Détails des Équipements

| Équipement   | Type       | IP Adresse       | Masque             | Rôle                   |
|--------------|------------|------------------|---------------------|------------------------|
| PC1          | PC-PT      | 192.168.1.2       | 255.255.255.0      | Hôte LAN 1             |
| PC2          | PC-PT      | 192.168.2.2       | 255.255.255.0      | Hôte LAN 2             |
| Router1      | Router-PT  | 192.168.1.1 (LAN) | 255.255.255.0      | Passerelle de PC1      |
|              |            | 10.10.0.1 (WAN)   | 255.255.255.252    | Vers Router2           |
| Router2      | Router-PT  | 192.168.2.1 (LAN) | 255.255.255.0      | Passerelle de PC2      |
|              |            | 10.10.0.2 (WAN)   | 255.255.255.252    | Vers Router1           |

---

## 📐 Sous-réseaux

- **LAN 1** : `192.168.1.0/24`
  - Hôte : `192.168.1.2`
  - Gateway : `192.168.1.1`

- **LAN 2** : `192.168.2.0/24`
  - Hôte : `192.168.2.2`
  - Gateway : `192.168.2.1`

- **Lien WAN** : `10.10.0.0/30`
  - Router1 : `10.10.0.1`
  - Router2 : `10.10.0.2`

---

## ⚙️ Étapes de Configuration

### Routeur 1
```bash
Router1> enable
Router1# configure terminal

# Interface LAN
Router1(config)# interface fastethernet0/0
Router1(config-if)# ip address 192.168.1.1 255.255.255.0
Router1(config-if)# no shutdown

# Interface WAN
Router1(config)# interface serial0/0/0
Router1(config-if)# ip address 10.10.0.1 255.255.255.252
Router1(config-if)# no shutdown

# Route statique vers LAN 2
Router1(config)# ip route 192.168.2.0 255.255.255.0 10.10.0.2

```


### Router 2

```bash
Router2> enable
Router2# configure terminal

# Interface LAN
Router2(config)# interface fastethernet0/0
Router2(config-if)# ip address 192.168.2.1 255.255.255.0
Router2(config-if)# no shutdown

# Interface WAN
Router2(config)# interface serial0/0/0
Router2(config-if)# ip address 10.10.0.2 255.255.255.252
Router2(config-if)# no shutdown

# Route statique vers LAN 1
Router2(config)# ip route 192.168.1.0 255.255.255.0 10.10.0.1
```

# 7 🌐 Topologie Routage entre deux LAN via deux routeurs et deux switchs

Ce scénario représente deux réseaux locaux (LAN) avec des post connecter a un swith connectés via un lien point-à-point entre deux routeurs. Chaque LAN contient 5 et 4 PC configuré avec une adresse IP statique.

---

## 📌 Détails des Équipements

| Équipement   | Type       | IP Adresse       | Masque             | Rôle                   |
|--------------|------------|------------------|---------------------|------------------------|
| PC1          | PC-PT      | 192.168.1.2       | 255.255.255.0      | Hôte LAN 1             |
| PC2          | PC-PT      | 192.168.1.3       | 255.255.255.0      | Hôte LAN 1             |
| PC3          | PC-PT      | 192.168.1.4       | 255.255.255.0      | Hôte LAN 1             |
| PC4          | PC-PT      | 192.168.1.5       | 255.255.255.0      | Hôte LAN 1             |
| PC5          | PC-PT      | 192.168.1.6       | 255.255.255.0      | Hôte LAN 1             |
| laptop0      | Laptoppt-PT| 192.168.2.2       | 255.255.255.0      | Hôte LAN 2             |
| PC2          | PC-PT      | 192.168.2.3       | 255.255.255.0      | Hôte LAN 2             |
| PC2          | PC-PT      | 192.168.2.4       | 255.255.255.0      | Hôte LAN 2             |
| PC2          | PC-PT      | 192.168.2.5       | 255.255.255.0      | Hôte LAN 2             |
| Router1      | Router-PT  | 192.168.1.1 (LAN) | 255.255.255.0      | Passerelle de PC1-5    |
|              |            | 10.10.0.1 (WAN)   | 255.255.255.252    | Vers Router2           |
| Router2      | Router-PT  | 192.168.2.1 (LAN) | 255.255.255.0      | Passerelle de PC2      |
|              |            | 10.10.0.2 (WAN)   | 255.255.255.252    | Vers Router1           |

---

## 📐 Sous-réseaux

- **LAN 1** : `192.168.1.0/24`
  - Hôte : `192.168.1.2`
  - Gateway : `192.168.1.1`

- **LAN 2** : `192.168.2.0/24`
  - Hôte : `192.168.2.2`
  - Gateway : `192.168.2.1`

- **Lien WAN** : `10.10.0.0/30`
  - Router1 : `10.10.0.1`
  - Router2 : `10.10.0.2`

---

## ⚙️ Étapes de Configuration

### Routeur 1
```bash
Router1> enable
Router1# configure terminal

# Interface LAN
Router1(config)# interface fastethernet0/0
Router1(config-if)# ip address 192.168.1.1 255.255.255.0
Router1(config-if)# no shutdown

# Interface WAN
Router1(config)# interface s2/0
Router1(config-if)# ip address 10.10.0.1 255.255.255.252
Router1(config-if)# no shutdown

# Route statique vers LAN 2
Router1(config)# ip route 192.168.2.0 255.255.255.0 10.10.0.2

```


### Router 2

```bash
Router2> enable
Router2# configure terminal

# Interface LAN
Router2(config)# interface fastethernet0/0
Router2(config-if)# ip address 192.168.2.1 255.255.255.0
Router2(config-if)# no shutdown

# Interface WAN
Router2(config)# interface s2/0
Router2(config-if)# ip address 10.10.0.2 255.255.255.252
Router2(config-if)# no shutdown

# Route statique vers LAN 1
Router2(config)# ip route 192.168.1.0 255.255.255.0 10.10.0.1
```


# 7 🌐 Topologie Routage entre deux LAN via deux routeurs et deux switchs

Ce scénario représente deux réseaux locaux (LAN) avec des post connecter a un swith connectés via un lien point-à-point entre deux routeurs. Chaque LAN contient 5 et 4 PC configuré avec une adresse IP statique.

---

## 📌 Détails des Équipements

| Équipement   | Type       | IP Adresse        | Masque             | Rôle                   |
|--------------|------------|-------------------|--------------------|------------------------|
| PC1          | PC-PT      | 192.168.1.194     | 255.255.255.192    | Hôte LAN 1             |
| PC2          | PC-PT      | 192.168.1.195     | 255.255.255.192    | Hôte LAN 1             |
| PC3          | PC-PT      | 192.168.1.196     | 255.255.255.192    | Hôte LAN 1             |
| PC4          | PC-PT      | 192.168.1.197     | 255.255.255.192    | Hôte LAN 1             |
| PC5          | PC-PT      | 192.168.1.198     | 255.255.255.192    | Hôte LAN 1             |
| laptop0      | Laptoppt-PT| 192.168.2.2       | 255.255.255.0      | Hôte LAN 2             |
| PC2          | PC-PT      | 192.168.2.3       | 255.255.255.0      | Hôte LAN 2             |
| PC2          | PC-PT      | 192.168.2.4       | 255.255.255.0      | Hôte LAN 2             |
| PC2          | PC-PT      | 192.168.2.5       | 255.255.255.0      | Hôte LAN 2             |
| PC2          | PC-PT      | 192.168.3.164     | 255.255.255.240    | Hôte LAN 3             |
| PC2          | PC-PT      | 192.168.3.165     | 255.255.255.240    | Hôte LAN 3             |
| PC2          | PC-PT      | 192.168.3.166     | 255.255.255.240    | Hôte LAN 3             |
| Router1      | Router-PT  | 192.168.1.193(LAN)| 255.255.255.0      | Passerelle de PC1-5    |
|              |            | 10.10.0.1 (WAN)   | 255.255.255.252    | Vers Router2           |
| Router2      | Router-PT  | 192.168.2.1 (LAN) | 255.255.255.0      | Passerelle de PC6-9    |
|              |            | 10.10.0.2 (WAN)   | 255.255.255.252    | Vers Router1           |
|              |            | 10.10.1.1 (WAN)   | 255.255.255.252    | Vers Router3           |
| Router3      | Router-PT  | 192.168.3.163(LAN)| 255.255.255.240    | Passerelle de PC10-12  |
|              |            | 10.10.1.2 (WAN)   | 255.255.255.252    | Vers Router2           |

---

## 📐 Sous-réseaux

- **LAN 1** : `192.168.1.192/26`
  - Hôte : `192.168.1.194`
  - Gateway : `192.168.1.193`

- **LAN 2** : `192.168.2.0/24`
  - Hôte : `192.168.2.2`
  - Gateway : `192.168.2.1`

  - **LAN 3** : `192.168.3.162/28`
  - Hôte : `192.168.3.164`
  - Gateway : `192.168.3.163`

- **Lien WAN** : `10.10.0.0/30`
  - Router1 : `10.10.0.1`
  - Router2 -> Router1 : `10.10.0.2` 
  - Router2 -> Router3 : `10.10.1.1`
  - Router3 : `10.10.1.2`
---

## ⚙️ Étapes de Configuration

### Routeur 1
```bash
Router1> enable
Router1# configure terminal

# Interface LAN
Router1(config)# interface fastethernet0/0
Router1(config-if)# ip address 192.168.1.193 255.255.255.192
Router1(config-if)# no shutdown

# Interface WAN
Router1(config)# interface s2/0
Router1(config-if)# ip address 10.10.0.1 255.255.255.252
Router1(config-if)# no shutdown

# Route statique vers LAN 2 et LAN 3
Router1(config)# ip route 192.168.3.160 255.255.255.240 10.10.0.2 
Router1(config)# ip route 192.168.2.0 255.255.255.0 10.10.0.2 

```


### Router 2

```bash
Router2> enable
Router2# configure terminal

# Interface LAN
Router2(config)# interface fastethernet0/0
Router2(config-if)# ip address 192.168.2.1 255.255.255.0
Router2(config-if)# no shutdown

# Interface WAN 1
Router2(config)# interface s2/0
Router2(config-if)# ip address 10.10.0.2 255.255.255.252
Router2(config-if)# no shutdown

# Interface WAN 2
Router2(config)# interface s3/0
Router2(config-if)# ip address 10.10.1.1 255.255.255.252
Router2(config-if)# no shutdown

# Route statique vers LAN 1 et LAN 3
Router2(config)# ip route 192.168.1.192 255.255.255.192 10.10.0.1 
Router2(config)# ip route 192.168.3.160 255.255.255.240 10.10.1.2
```


### Router 3

```bash
Router3> enable
Router3# configure terminal

# Interface LAN
Router3(config)# interface fastethernet0/0
Router3(config-if)# ip address 192.168.3.163 255.255.255.240
Router3(config-if)# no shutdown

# Interface WAN
Router3(config)# interface s2/0
Router3(config-if)# ip address 10.10.1.2 255.255.255.252
Router3(config-if)# no shutdown

# Route statique vers LAN 1 et LAN 2
Router3(config)# ip route 192.168.1.192 255.255.255.192 10.10.1.1 
Router3(config)# ip route 192.168.2.0 255.255.255.0 10.10.1.1 
```


## 🧠 Connaissances acquises (complétée)
Principes fondamentaux du sous-réseautage

Types de câbles appropriés (croisés/droits)

Adressage IP et compréhension du binaire

Utilisation de commutateurs (Switches) et de concentrateurs (Hubs)

Connectivité de PC à PC

Éviter les conflits d'adresses IP

Configuration de routes statiques entre plusieurs sous-réseaux

Utilisation de liens point-à-point avec un masque /30 (idéal pour les connexions WAN)

Compréhension de l’adressage IP avancé (ex. : /29, /27, /30)

Gestion des VLAN implicites à travers des switches (même si non configurés explicitement)

Déploiement de services réseau essentiels : DNS, DHCP, FTP, HTTPS

Utilisation d’un serveur DHCP pour l’attribution automatique d’adresses IP

Configuration et test des services de couche application (FTP, DNS, HTTPS)

Communication inter-réseaux via des routeurs

Vérification de la connectivité avec la commande ping et diagnostic de réseau de base

Topologie en étoile et maillage partiel dans les infrastructures réseau

Configuration d’une passerelle par défaut sur les hôtes pour accéder aux autres réseaux


# 📂 Fichiers
deep-in-net/<br />
├── README.md<br />
├── ex01.pkt<br />
├── ex02.pkt<br />
├── ex03.pkt<br />
├── ex04.pkt<br />
├── ex05.pkt<br />
├── ex06.pkt<br />
├── ex07.pkt<br />
└── ex08.pkt