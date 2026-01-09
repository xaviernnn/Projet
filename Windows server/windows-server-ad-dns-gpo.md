# 🖥️ Windows Server 2022 – Active Directory, DNS & GPO

## 📌 Rôle du serveur
Ce serveur Windows Server 2022 est le **contrôleur de domaine principal** de l’infrastructure.  
Il assure la **gestion centralisée des identités**, la **résolution DNS interne** et l’application des **stratégies de sécurité via les GPO**.

Il constitue un élément **critique** du système d’information.

---

## 🎯 Objectifs
- Centraliser la gestion des utilisateurs et des machines
- Fournir un service DNS interne fiable
- Appliquer des stratégies de sécurité via les GPO
- Structurer l’environnement Active Directory d’une PME

---

## 🧱 Informations générales

| Élément              | Valeur |
|---------------------|--------|
| OS                  | Windows Server 2022 |
| Rôles installés     | AD DS, DNS |
| Type                | Contrôleur de domaine |
| Nom du serveur      | WIN-4HB9EOQPD8U |
| Domaine             | xavierneveu.local |
| Adresse IP          | 192.168.247.10 |
| Passerelle          | 192.168.247.5 (pfSense) |
| DNS primaire        | 127.0.0.1 |
| DNS secondaire      | — |

---

## 🌐 Intégration réseau
- Serveur situé dans le **LAN interne**
- Adresse IP **statique**
- Résolution DNS assurée localement
- Accessible depuis :
  - Machines internes
  - Utilisateurs VPN (Tailscale) (uniquement pour auth)

---

## 🗂️ Active Directory (AD DS)

### 🔹 Structure du domaine
- **Forêt** : Unique
- **Domaine** : xavierneveu.local
- **Niveau fonctionnel** : Windows Server 2022


## 🌍 DNS

### 🔹 Rôle
- Résolution de noms interne
- Intégration avec Active Directory
- Support des services AD

### 🔹 Configuration
- Zone principale intégrée à AD
- Mise à jour dynamique autorisée
- Transferts de zone désactivés (sécurité)

### 🔹 enregistrements
- 247.168.192.in-addr.arpa (enregistrement inversé pour NAS)
- truenas.xavierneveu.local 
---

## 📜 Stratégies de groupe (GPO)

### 🔹 Objectifs des GPO
- Renforcer la sécurité
- Standardiser les postes clients
- Appliquer des règles utilisateurs et machines

### 🔹 Exemples de GPO mises en place
- Politique de mot de passe renforcée + durée de vie
- Verrouillage automatique de session

---

## 🔐 Sécurité
- Accès administrateur restreint
- Comptes à privilèges séparés
- Journaux d’événements surveillés

