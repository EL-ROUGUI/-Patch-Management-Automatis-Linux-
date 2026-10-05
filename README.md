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
2. **Exécution du patching** : Playbook Ansible `playbook.yml`
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

| Fichier / Dossier        | Description                                        |
|--------------------------|----------------------------------------------------|
| `Vagrantfile`            | 3 VMs Ubuntu 22.04 (`server01`–`server03`, 192.168.56.11–13) + provisioning Node Exporter |
| `playbook.yml`           | Playbook Ansible idempotent : patchs APT + traçabilité dans `patching_activity.log` |
| `inventory.ini`          | Inventaire Ansible des 3 serveurs cibles           |
| `patch_project_os.zip`   | Archive complète : projet Ansible, exports dashboard Grafana, état Vagrant |
| `README.md`              | Documentation du projet                            |

> Les fichiers à la racine sont extraits de l'archive `patch_project_os.zip`, qui contient l'intégralité du projet (logs d'exécution, exports Grafana).

---

## 🧠 Compétences mises en pratique

- Création d’un playbook idempotent
- Automatisation d’inventaire multi-hôte
- Sécurisation des mises à jour système
- Visualisation des métriques système
- Gestion de projet DevOps minimal

---


