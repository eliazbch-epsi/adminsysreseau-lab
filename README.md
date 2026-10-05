# AdminSysReseau Lab

Bienvenue sur mon laboratoire personnel d'administration systèmes et réseaux.

## À propos

Bonjour, je m'appelle Eliaz Bouchon, j'ai 25 ans et je suis étudiant en administration systèmes et réseaux à l'EPSI de Nantes.

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
- [ ] DHCP
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

<img width="423" height="330" alt="image" src="https://github.com/user-attachments/assets/73290ef5-eb40-4809-b2b0-bd49b8580ee4" />

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

<img width="429" height="353" alt="image" src="https://github.com/user-attachments/assets/2e476880-40c6-468f-82ab-9a8d710ab74a" />

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

- [ ] DHCP
- [ ] DNS pratique
- [ ] VLAN
- [ ] Linux Ubuntu Server
- [ ] SSH
- [ ] Windows Server
- [ ] Active Directory
- [ ] PowerShell
