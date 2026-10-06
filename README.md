# AdminSysReseau Lab

Bienvenue sur mon laboratoire personnel d'administration systèmes et réseaux.

## À propos

Je m'appelle Eliaz Bouchon, j'ai 25 ans et je suis étudiant en administration systèmes et réseaux à l'EPSI de Nantes.

Ce dépôt contient mes projets, mes notes et mes laboratoires réalisés pendant mon apprentissage sur Cisco Packet Tracer.

## Compétences étudiées

- Réseau
- IPv4
- DNS
- DHCP
- Switch (Commutateur)
- Routeur
- Passerelle
- Vlan
- Linux
- Windows Server
- Active directory

## Progression

- [x] IPv4
- [x] Masque de sous-réseau
- [x] Switch
- [x] Routeur
- [x] Passerelle
- [x] DHCP
- [x] DNS pratique
- [ ] VLAN
- [ ] Linux
- [ ] Windows Server
- [ ] Active Directory

---

# Projets

## Projet 1 - Communication dans le même réseau

### Objectif

Faire communiquer deux machines dans le même réseau à l'aide d'un switch.

### Topologie

```text
PC1 --- Switch (Commutateur) --- PC2
```

### Capture

<img width="413" height="257" alt="image" src="https://github.com/user-attachments/assets/182e9946-dd04-4a51-9e96-fe07984e6f85" />

### Configuration

#### PC1

```text
192.168.1.10
```

#### PC2

```text
192.168.1.20
```

#### Masque de sous-réseau

```text
255.255.255.0
```

### Test

```bash
ping 192.168.1.20
```

### Résultat

```text
4 paquets envoyés
4 paquets reçus
0 paquet perdu
```

### Ce que j'ai appris

- Configurer une adresse IPv4
- Configurer un masque de sous-réseau
- Utiliser un switch (commutateur)
- Tester la connectivité avec la commande ping
- Comprendre la communication dans un même réseau

### Explication réseau

Les deux machines appartiennent au réseau :

```text
192.168.1.0/24
```

Elles peuvent donc communiquer directement à travers le switch sans utiliser de routeur ni de passerelle.

---

## Projet 2 - Communication entre deux réseaux

### Objectif

Faire communiquer deux réseaux différents grâce à un routeur.

### Topologie

```text
PC1 --- Switch1 --- Routeur --- Switch2 --- PC2
```

### Capture

<img width="608" height="140" alt="image" src="https://github.com/user-attachments/assets/a65db666-17d5-40a0-8117-dd33580f58f5" />

### Réseau 1

```text
Réseau : 192.168.1.0/24

PC1 : 192.168.1.10
Passerelle : 192.168.1.1
```

### Réseau 2

```text
Réseau : 192.168.2.0/24

PC2 : 192.168.2.10
Passerelle : 192.168.2.1
```

### Test

```bash
ping 192.168.2.10
```

### Résultat

```text
Communication réussie entre les deux réseaux.
```

### Ce que j'ai appris

- Configurer un routeur
- Comprendre le rôle d'une passerelle
- Comprendre le routage
- Faire communiquer des réseaux différents
- Utiliser la commande ping pour tester la connectivité

### Explication réseau

PC1 constate que l'adresse de destination :

```text
192.168.2.10
```

n'appartient pas à son réseau local :

```text
192.168.1.0/24
```

PC1 envoie donc les paquets à sa passerelle :

```text
192.168.1.1
```

Le routeur reçoit les paquets, détermine le réseau de destination et les transmet vers :

```text
192.168.2.0/24
```

afin de joindre PC2.

---

## Prochaines étapes

- [x] DHCP
- [x] DNS pratique
- [ ] VLAN
- [ ] Linux Ubuntu Server
- [ ] SSH
- [ ] Windows Server
- [ ] Active Directory
- [ ] PowerShell

## Projet 3 - DHCP
 
### Objectif
 
Attribuer automatiquement une configuration réseau aux postes du réseau grâce à un serveur DHCP.
 
### Topologie
 
```text
PC1 ---- Switch1 (Commutateur) ---- Server1
```
 
### Capture
 
<img width="453" height="136" alt="image" src="https://github.com/user-attachments/assets/0150a18f-58aa-4f43-be5c-6be3dd5c1ece" />

### Équipement utilisé
 
```text
- Un PC (machine) nommé PC1
- Un switch nommé Switch1
- Un serveur nommé Server1
```
 
### Configuration du serveur DHCP
 
```text
Adresse IP du serveur : 192.168.1.100
 
Masque de sous-réseau : 255.255.255.0
 
Passerelle : 192.168.1.1
```
 
### Configuration de la plage DHCP
 
```text
Nom du pool : test
 
Adresse de départ : 192.168.1.110
 
Masque de sous-réseau : 255.255.255.0
 
Passerelle : 192.168.1.1
 
DNS : 0.0.0.0
 
Nombre maximum d'utilisateurs : 156
```
 
### Test
 
```text
1. J'ai configuré une adresse IP statique sur le serveur.
 
2. J'ai activé le service DHCP sur le serveur.
 
3. J'ai créé un pool DHCP contenant une plage d'adresses IP disponibles.
 
4. Sur le poste PC1, j'ai ouvert :
 
Desktop → IP Configuration
 
5. J'ai sélectionné DHCP afin de demander automatiquement une configuration réseau.
 
6. Après actualisation, le poste a reçu automatiquement sa configuration réseau depuis le serveur DHCP.
```
 
### Résultat
 
```text
DHCP request successful

le server DHCP a attribué automatiquement une adresse ip au pc1 
```
 
Le poste client a obtenu automatiquement :
 
```text
Adresse IP : 192.168.1.110
Masque : 255.255.255.0
Passerelle : 192.168.1.1
```
 
### Ce que j'ai appris
 
- Configurer un serveur DHCP
- Créer un pool DHCP
- Attribuer automatiquement une configuration réseau à un poste
- Comprendre le rôle du DHCP
- Diagnostiquer un problème d'attribution d'adresse IP
- Comprendre la différence entre une adresse IP statique et dynamique
- Reconnaître une adresse APIPA (169.254.x.x)
 
### Explication réseau
 
Le serveur DHCP permet de configurer automatiquement :
 
```text
- une adresse IP
- un masque de sous-réseau
- une passerelle par défaut
- un serveur DNS
```
 
Lorsqu'un poste démarre, il peut demander automatiquement une configuration réseau au serveur DHCP.
 
Le serveur DHCP lui attribue alors automatiquement :
 
```text
- une adresse IP
- un masque de sous-réseau
- une passerelle par défaut
- un serveur DNS
```
 
L'utilisateur n'a donc plus besoin de configurer manuellement :
 
```text
- l'adresse IP
- le masque de sous-réseau
- la passerelle
- le DNS
```
 
Grâce au DHCP, la configuration de plusieurs postes sur un réseau est beaucoup plus rapide et plus simple.
 
### Difficultés rencontrées
 
```text
- Comprendre le fonctionnement d'un pool DHCP.
- Comprendre quelles adresses IP attribuer.
- Comprendre l'utilité du DHCP.
- Tester la distribution automatique d'une adresse IP.
- Identifier les erreurs de configuration.
```
 
### Solution apportée
 
```text
J'ai configuré une adresse IP statique sur le serveur DHCP.
 
J'ai créé plusieurs pools DHCP et j'ai dû identifier celui qui était réellement utilisé.
 
Après avoir corrigé ma configuration, le poste client a pu obtenir automatiquement une adresse IP depuis le serveur DHCP.
 
J'ai également appris à reconnaître une adresse APIPA (169.254.x.x), qui indique généralement qu'un poste n'a pas réussi à contacter un serveur DHCP.
```

## Projet 4 - DNS
 
### Objectif
 
Mettre en place un serveur DNS capable de résoudre un nom de domaine en adresse IP.
 
### Topologie
 
```text
PC1 ---- Switch1 ---- Server1
```
 
### Capture
 
<img width="468" height="143" alt="image" src="https://github.com/user-attachments/assets/f77ab266-5dca-4bf6-a508-0763ad4ddc38" />
 
### Équipement utilisé
 
```text
- Un poste client nommé PC1
- Un switch nommé Switch1
- Un serveur DNS nommé Server1
```
 
### Configuration du serveur DNS
 
```text
Adresse IP du serveur : 192.168.1.100
 
Masque de sous-réseau : 255.255.255.0
 
DNS : 192.168.1.100
```
 
### Configuration du poste client
 
```text
Adresse IP : 192.168.1.110
 
Masque de sous-réseau : 255.255.255.0
 
DNS : 192.168.1.100
```
 
### Configuration DNS
 
```text
Nom de domaine : serveur.local
 
Adresse IP associée : 192.168.1.100
 
Type : A Record
```
 
### Test
 
```bash
nslookup serveur.local
```
 
### Résultat
 
```text
Name : serveur.local
Address : 192.168.1.100
```
 
Le serveur DNS a correctement converti le nom de domaine en adresse IP.
 
### Ce que j'ai appris
 
- Configurer un serveur DNS
- Créer un enregistrement DNS (A Record)
- Résoudre un nom de domaine en adresse IP
- Utiliser la commande nslookup
- Comprendre le rôle du DNS dans un réseau
 
### Explication réseau
 
Le DNS permet de traduire un nom de domaine en adresse IP.
 
Par exemple :
 
```text
serveur.local
↓
192.168.1.100
```
 
Les utilisateurs retiennent plus facilement un nom qu'une adresse IP.
 
Lorsqu'un utilisateur saisit :
 
```text
serveur.local
```
 
le poste envoie une requête au serveur DNS.
 
Le serveur DNS répond avec l'adresse IP associée :
 
```text
192.168.1.100
```
 
Le poste peut alors communiquer avec le serveur sans que l'utilisateur ait besoin de connaître son adresse IP.
 
### Difficultés rencontrées
 
```text
- Comprendre la différence entre un nom de domaine et une adresse IP.
- Configurer correctement le serveur DNS.
- Configurer l'adresse du serveur DNS sur le poste client.
- Comprendre pourquoi le nom de domaine n'était pas résolu.
```
 
### Solution apportée
 
```text
J'ai créé un enregistrement DNS de type A Record.
 
J'ai associé le nom serveur.local à l'adresse IP 192.168.1.100.
 
J'ai ensuite configuré PC1 afin qu'il utilise le serveur DNS 192.168.1.100.
 
Enfin, j'ai vérifié le fonctionnement avec la commande nslookup serveur.local qui a correctement retourné l'adresse IP du serveur.
```

## Projet 5 - VLAN
 
### Objectif
 
Segmenter un réseau en plusieurs réseaux logiques grâce aux VLAN afin d'isoler la communication entre certains postes tout en utilisant un seul switch.
 
### Topologie
 
```text
PC1
|
|
Switch1 ----- PC3
|
|
PC2
|
|
PC4
```
 
### Capture
 
<img width="665" height="418" alt="image" src="https://github.com/user-attachments/assets/897922d9-9c49-4cbc-a75b-b1b4dc30e7de" />
 
### Équipement utilisé
 
```text
- Deux postes clients dans le VLAN 10 (PC1 et PC2)
- Deux postes clients dans le VLAN 20 (PC3 et PC4)
- Un switch nommé Switch1
```
 
### Configuration des VLAN
 
```text
VLAN 10
 
PC1 : 192.168.1.10
PC2 : 192.168.1.20
```
 
```text
VLAN 20
 
PC3 : 192.168.1.30
PC4 : 192.168.1.40
```
 
### Affectation des ports
 
```text
Fa0/1 → VLAN 10
Fa0/2 → VLAN 10
 
Fa0/3 → VLAN 20
Fa0/4 → VLAN 20
```
 
### Tests réalisés
 
Depuis PC1 :
 
```bash
ping 192.168.1.20
```
 
Résultat :
 
```text
Réussi
```
 
Depuis PC1 :
 
```bash
ping 192.168.1.30
```
 
Résultat :
 
```text
Échec
```
 
Depuis PC1 :
 
```bash
ping 192.168.1.40
```
 
Résultat :
 
```text
Échec
```
 
### Résultat
 
```text
PC1 peut communiquer avec PC2.
 
PC1 ne peut pas communiquer avec PC3 ni PC4.
```
 
Le VLAN isole correctement les deux groupes de machines.
 
### Ce que j'ai appris
 
- Créer des VLAN sur un switch
- Affecter des ports à des VLAN
- Comprendre le principe de segmentation réseau
- Tester la communication entre plusieurs VLAN
- Vérifier l'isolation des postes avec ping
 
### Explication réseau
 
Un VLAN (Virtual LAN) permet de créer plusieurs réseaux logiques sur un même switch.
 
Dans ce projet :
 
```text
VLAN 10 :
PC1 et PC2
```
 
```text
VLAN 20 :
PC3 et PC4
```
 
Les postes appartenant au même VLAN peuvent communiquer entre eux.
 
Les postes appartenant à des VLAN différents ne peuvent pas communiquer directement, même s'ils sont branchés sur le même switch.
 
Grâce aux VLAN, il est possible de séparer plusieurs services ou départements d'une entreprise sur une même infrastructure réseau.
 
### Difficultés rencontrées
 
```text
- Comprendre le fonctionnement des VLAN.
- Créer les VLAN sur le switch.
- Affecter les bons ports aux bons VLAN.
- Vérifier que les machines étaient correctement isolées.
```
 
### Solution apportée
 
```text
J'ai créé un VLAN 10 et un VLAN 20 sur le switch.
 
J'ai ensuite affecté chaque port du switch au VLAN correspondant.
 
Enfin, j'ai vérifié le bon fonctionnement à l'aide de la commande ping.
 
Les tests ont confirmé que les postes d'un même VLAN communiquent entre eux tandis que les postes de VLAN différents restent isolés.
```

## À retenir
 
```text
IP = identifie une machine
 
Masque = sépare la partie réseau de la partie machine
 
Switch = relie les machines d'un même réseau
 
Routeur = relie plusieurs réseaux différents
 
Passerelle = porte de sortie d'un réseau local
 
DHCP = attribue automatiquement :
- IP
- Masque
- Passerelle
- DNS
 
APIPA (169.254.x.x) =
le PC n'a pas réussi à joindre un serveur DHCP
 
DNS = traduit un nom de domaine en adresse IP
 
Exemple :
 
serveur.local
↓
192.168.1.100
 
Même réseau
→ communication directe
 
Réseaux différents
→ routeur obligatoire

VLAN = Virtual Lan

Permet de créer plusieurs réseaux logiques
sur un même switch.
 
Même VLAN
→ communication autorisée
 
VLAN différents
→ communication impossible
(sans routage inter-VLAN)
```
