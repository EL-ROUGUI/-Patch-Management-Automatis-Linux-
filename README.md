# 🛡️ Patch Management Automatisé (Linux)

Ce projet met en place une solution simple et automatisée de gestion des correctifs de sécurité sur des serveurs Linux (Ubuntu LTS) en environnement virtuel.

## 🎯 Objectif

Automatiser l'application des correctifs de sécurité sur des machines Ubuntu, tout en assurant :
- La traçabilité des mises à jour
- L'observabilité via un tableau de bord
- Un déploiement reproductible

> 📌 Projet réalisé dans le cadre d’un module DevOps/Cybersécurité.

---

## 🧱 Architecture

- 📦 **Vagrant** : provisionne plusieurs VMs Ubuntu LTS
- ⚙️ **Ansible** : applique les correctifs avec un playbook idempotent
- 📊 **Grafana** : affiche un tableau de bord de suivi des patchs
- 🔍 **Logs** : chaque machine garde la trace des packages mis à jour

---

## 🧪 Fonctionnement

1. **Provisionnement** : Lancement des VMs avec `Vagrantfile`
2. **Exécution du patching** : Playbook Ansible `patch.yml`
3. **Monitoring** : Un agent collecte le nombre de packages patchés et l'envoie à Grafana (via Prometheus/local logs)
4. **Visualisation** : Tableau de bord en temps réel (`N patched`, date, machine, etc.)

---

## 🛠️ Technologies utilisées

- **Vagrant**
- **Ansible**
- **Ubuntu 22.04 LTS**
- **Grafana**
- **Prometheus ou logs locaux**
- **Shell scripting (log / audit)**

---

## 📂 Fichiers du projet

| Fichier / Dossier        | Description                           |
|--------------------------|---------------------------------------|
| `Vagrantfile`            | Configuration de l'inventaire virtuel |
| `playbooks/patch.yml`    | Playbook Ansible pour le patching     |
| `logs/`                  | Dossiers de logs des patchs appliqués |
| `grafana/`               | Configurations du dashboard (JSON)    |
| `README.md`              | Documentation du projet               |

---

## 🧠 Compétences mises en pratique

- Création d’un playbook idempotent
- Automatisation d’inventaire multi-hôte
- Sécurisation des mises à jour système
- Visualisation des métriques système
- Gestion de projet DevOps minimal

---

