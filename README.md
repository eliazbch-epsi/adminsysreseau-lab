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

## Progression

- [x] IPv4
- [x] Masque de sous-réseau
- [x] Switch
- [x] Routeur
- [x] Passerelle
- [x] DHCP
- [ ] DNS pratique
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
- [ ] DNS pratique
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
 
<img width="496" height="152" alt="image" src="https://github.com/user-attachments/assets/c394815a-934c-44ee-abe8-cf2488836e39" />

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
