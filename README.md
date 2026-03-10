# Test d'entrée Mastère Cybersécurité - La Plateforme_

**Candidat :** Maxime CHAPMAN

## Exercice 01 : Packet Tracer - MiniLab Réseau

### Description du projet
Réalisation d'une infrastructure réseau segmentée pour trois bureaux. 

### Détails Techniques
- **Segmentation :** Création de 4 VLANs (1, 10, 20, 30).
- **Routage :** Mise en place d'un routage Inter-VLAN (Router-on-a-stick) sur un Cisco 1941.
- **Adressage :** Configuration d'un serveur DHCP centralisé sur le routeur pour une distribution automatique des adresses IP.
- **Uplinks :** Liaisons Trunks (IEEE 802.1Q) configurées sur les ports 1 et 9 de chaque switch.

### Validation
La connectivité a été validée par des tests ICMP (Ping) entre les différents VLANs et par la vérification de l'attribution correcte des baux DHCP sur les postes de travail.
