# 🏗️ Lab d’Infrastructure Réseau – Environnement PME

## 📌 Introduction
Ce projet consiste en la mise en place d’un **lab d’infrastructure réseau simulant un environnement d’entreprise réaliste**, proche des besoins d’une PME.  
Il couvre la **sécurité réseau**, la **gestion centralisée**, la **virtualisation**, le **stockage**, la **supervision**, la **sauvegarde** et l’**accès distant sécurisé**.

L’objectif principal est de **monter en compétence sur une infrastructure complète**, cohérente et opérationnelle, intégrant des technologies largement utilisées en entreprise.

---

## 🎯 Objectifs du lab
- Simuler un réseau interne sécurisé
- Contrôler l’accès Internet via un pare-feu
- Mettre en place un accès distant sécurisé via VPN
- Déployer des services centraux :
  - Active Directory & DNS
  - Stockage réseau
  - Supervision
  - Sauvegarde
- Approcher une architecture réelle de PME

---

## 🌐 Vue globale de l’architecture
L’infrastructure est organisée autour de **trois zones réseau principales** :

- **Réseau interne (LAN)**  
  Héberge les serveurs, services critiques et postes clients internes.

- **Accès distant sécurisé (VPN)**  
  Permet aux utilisateurs distants d’accéder aux ressources internes (NAS, services AD).

- **Accès Internet**  
  Contrôlé, filtré et sécurisé via un pare-feu central **pfSense**.

👉 **pfSense** est le point central de l’architecture : sécurité, routage, NAT et VPN.

---

## 🧱 Équipements et rôles

### 🔥 pfSense
- Pare-feu principal
- Routage inter-réseaux
- NAT vers Internet
- Passerelle par défaut
- VPN (Tailscale)
- Point central de sécurité

### 🖥️ Windows Server 2022
**Serveur 1 – Contrôleur de domaine**
- Active Directory
- DNS
- Gestion centralisée des utilisateurs et machines

**Serveur 2 – Serveur membre**
- Intégré au domaine AD
- Plateforme de tests

### 🗄️ TrueNAS
- Stockage réseau centralisé
- Partages de fichiers internes
- Accès sécurisé via VPN

### 📊 Serveur de supervision (Zabbix)
- Monitoring des serveurs et équipements réseau
- Surveillance des performances
- Alertes en cas d’incident

### 💾 Serveur de sauvegarde
- Sauvegardes via `rsync`
- Protection des données critiques
- Possibilité de restauration

### 🧪 Proxmox
- Hyperviseur
- Hébergement des machines virtuelles
- Gestion centralisée des ressources

### 📱 Client mobile
- Accès réseau uniquement via VPN
- Simulation d’un utilisateur distant

---

## 📡 Plan d’adressage IP

### Réseau interne : `192.168.247.0/24`

| Équipement                         | Adresse IP        |
|----------------------------------|-------------------|
| pfSense (passerelle)             | 192.168.247.5     |
| TrueNAS                          | 192.168.247.6     |
| Contrôleur de domaine / DNS      | 192.168.247.10    |
| Serveur de sauvegarde            | 192.168.247.11    |
| Serveur Zabbix                   | 192.168.247.12    |
| Postes clients                   | DHCP              |

🔒 Les équipements critiques utilisent des **IP statiques**, les postes clients sont configurés en **DHCP**.

---

## 🛠️ Services réseau

- **DHCP**  
  Attribution automatique des adresses IP aux clients

- **DNS**  
  Résolution de noms centralisée via le contrôleur de domaine

- **Active Directory**  
  Gestion des utilisateurs, groupes, machines et stratégies de sécurité

- **VPN (Tailscale)**  
  Accès distant sécurisé aux ressources internes

- **NAS (TrueNAS)**  
  Stockage et partage de fichiers

- **Supervision (Zabbix)**  
  Surveillance de l’infrastructure et alertes

- **Sauvegardes (rsync)**  
  Protection des données et reprise après incident

- **Virtualisation (Proxmox)**  
  Hébergement et gestion des machines virtuelles

---

## 🚀 Cas d’usage
- Simulation d’une infrastructure PME
- Tests de sécurité réseau
- Apprentissage Active Directory
- Mise en place de VPN sécurisé
- Supervision et gestion d’incidents
- Sauvegarde et restauration de données

---

## 🧩 Dépendances & technologies
- pfSense
- Windows Server 2022
- Proxmox VE
- TrueNAS
- Zabbix
- Tailscale
- rsync


---

## 👤 Contributeur(s)
- Projet personnel / Lab de formation

---

## 📄 Licence
Projet à but pédagogique et personnel.  
Licence à définir selon le contexte d’utilisation.
