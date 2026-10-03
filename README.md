# AdminSysReseau Lab
 
Bienvenue sur mon laboratoire personnel d'administration systèmes et réseaux.
 
## À propos
 
Je suis étudiant en administration systèmes et réseaux à l'EPSI de Nantes.
 
Ce dépôt contient mes projets, mes notes et mes laboratoires réalisés pendant mon apprentissage sur Cicso Packet Tracker.
 
## Compétences étudiées
 
- Réseau
- IPv4
- DNS
- DHCP
- Switch
- Routeur
- Passerelle
- Linux
- Windows Server
 
## Projets

### Projet 1 - Communication entre deux réseaux
 
## Objectif
 
Faire communiquer deux machines dans le même réseau à l'aide d'un switch.
 
## Topologie
 
PC0 --- Switch --- PC1
 
## Capture
 
<img width="458" height="368" alt="image" src="https://github.com/user-attachments/assets/5a2e0e88-62c9-4b3c-88dd-ac199d8792ad" />
 
## Configuration
 
### PC0
 
```text
192.168.1.10
```
 
### PC1
 
```text
192.168.1.20
```
 
### Masque De Sous-Réseau
 
```text
255.255.255.0
```
 
## Test
 
```bash
ping 192.168.1.20
```
 
## Résultat
 
```text
4 paquets envoyés
4 paquets reçus
0 paquet perdu
```
 
## Ce que j'ai appris
 
- Configurer une adresse IPv4
- Configurer un masque de sous-réseau
- Utiliser un switch
- Tester la connectivité avec ping
- Comprendre la communication dans un même réseau
 
## Explication réseau
 
Les deux machines appartiennent au réseau :
 
```text
192.168.1.0/24
```
 
Elles peuvent donc communiquer directement à travers le switch sans utiliser de routeur ni de passerelle.

