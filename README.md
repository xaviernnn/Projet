# Projet
🎯 Objectif du lab
Ce lab d’infrastructure réseau a pour objectif de simuler un environnement d’entreprise réaliste, incluant :
un réseau interne sécurisé,

un accès Internet contrôlé,

un accès distant sécurisé via VPN,

des services centraux (AD, DNS, stockage, supervision, sauvegarde).

L’objectif est de monter en compétence sur une infrastructure complète, proche des besoins réels d’une PME.

🌐 Vue globale de l’architecture
L’infrastructure est organisée autour de trois zones réseau principales :
Réseau interne (LAN)
 → héberge les serveurs, services critiques et machines internes.

Accès distant sécurisé (VPN)
 → permet aux utilisateurs distants d’accéder aux ressources internes (NAS, services AD).

Accès Internet
 → contrôlé et filtré via un pare-feu central (pfSense).

Le pare-feu pfSense est le point central de l’architecture : sécurité, routage, NAT et VPN.

🧱 Équipements et rôles
🔥 pfSense
Pare-feu principal

Routage inter-réseaux

NAT vers Internet

Passerelle par défaut

VPN (Tailscale)

Point central de sécurité

🖥️ Windows Server 2022
Serveur 1 – Contrôleur de domaine
Active Directory

DNS

Gestion centralisée des utilisateurs et machines

Serveur 2 – Serveur membre
Plateforme de tests

Intégration au domaine AD

🗄️ TrueNAS
Stockage réseau centralisé

Partages de fichiers internes

Accès sécurisé via VPN

📊 Serveur de supervision (Zabbix)
Monitoring des serveurs et équipements réseau

Surveillance de la disponibilité et des performances

Alertes en cas d’incident

💾 Serveur de sauvegarde
Sauvegardes via rsync

Protection des données critiques

Possibilité de restauration

🧪 Proxmox
Hyperviseur

Hébergement des machines virtuelles

Gestion centralisée des ressources

📱 Client mobile
Accès réseau uniquement via VPN

Simulation d’un utilisateur distant

📡 Plan d’adressage IP
Réseau interne : 192.168.247.0/24
Équipement
Adresse IP
pfSense (passerelle)
192.168.247.5
TrueNAS
192.168.247.6
Contrôleur de domaine / DNS
192.168.247.10
Serveur de backup
192.168.247.11
Serveur Zabbix
192.168.247.12
Autres machines
DHCP

Les équipements critiques utilisent des IP statiques, les postes clients sont configurés en DHCP.

🛠️ Services réseau
DHCP
 Attribution automatique des adresses IP aux clients.

DNS
 Résolution de noms centralisée via le contrôleur de domaine.

Active Directory
 Gestion des utilisateurs, groupes, machines et stratégies de sécurité.

VPN (Tailscale)
 Accès distant sécurisé aux ressources internes.

NAS
 Stockage et partage de fichiers.

Supervision (Zabbix)
 Surveillance de l’infrastructure et alertes.

Sauvegardes (rsync)
 Protection des données et reprise après incident.

Virtualisation (Proxmox)
 Hébergement et gestion des machines virtuelles.
