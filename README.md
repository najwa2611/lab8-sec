
# 🔒 Lab d'Audit de Sécurité Mobile

## 📋 Description

Laboratoire d'audit défensif d'application mobile utilisant BeVigil et Yaazhini pour collecter des signaux d'exposition, trier les résultats et produire un rapport selon les standards OWASP.

## 🛠️ Outils Requis

| Outil | Type | Obtention |
|-------|------|-----------|
| **BeVigil** | Plateforme en ligne | Accès fourni par l'enseignant |
| **Yaazhini** | Logiciel à installer | Téléchargement fourni par l'enseignant |

### Prérequis
- Java 1.8 ou supérieur
- APK pédagogique fourni par l'enseignant

## 🚀 Installation

### 1. Créer la structure du projet
```powershell
mkdir lab-mobile-security
cd lab-mobile-security
mkdir 00-scope, 01-bevigil, 02-yaazhini, 03-triage, 04-report
```

### 2. Installer Yaazhini
- Télécharger l'installateur fourni par l'enseignant
- Exécuter le fichier et suivre l'assistant

### 3. Vérifier Java
```powershell
java -version
```

## 📊 Workflow

```
Préparation → BeVigil (externe) → Yaazhini (interne) → Triage → Normalisation → Corrélation OWASP → Rapport → Clôture
```

## 📝 Étapes du Lab

### Task 0 - Périmètre (5 min)
Créer `00-scope/scope.md` avec :
- Nom de la cible autorisée
- Preuve d'autorisation
- Limites explicites

### Task 1 - Workspace (10 min)
- Créer l'arborescence
- Remplir `analyse_info.txt`
- Initialiser `commands.log`

### Task 2 - Artefact (10 min)
- Copier l'APK dans `00-scope/`
- Calculer le hash SHA-256

### Task 3 - BeVigil (15 min)
- Accéder à BeVigil
- Créer un projet `LAB-BEGINNER-YYYYMMDD`
- Exporter les résultats dans `01-bevigil/`

### Task 4 - Collecte BeVigil (20 min)
Documenter dans `01-bevigil/bevigil_notes.md` :
- Domaines et sous-domaines
- Endpoints et APIs
- URLs et technologies

### Task 5 - Yaazhini (15 min)
Lancer l'analyse sur l'APK et sauvegarder le rapport dans `02-yaazhini/`

### Task 6 - Collecte Yaazhini (20 min)
Documenter dans `02-yaazhini/yaazhini_notes.md` :
- Secrets et clés exposées
- Endpoints hardcodés
- Configurations sensibles
- Permissions

### Task 7 - Normalisation (15 min)
Créer `03-triage/triage.csv` avec :
```
ID,Source,Élément,Preuve,Confiance,Sévérité,Impact,Recommandation,Référence OWASP,Statut
```

### Task 8 - Corrélation OWASP (15 min)
Mapper les constats aux standards OWASP MASVS dans `03-triage/owasp_mapping.md`

### Task 9 - Rapport (20 min)
Rédiger `04-report/rapport_final.md` :
- Résumé exécutif
- Top 5 constats
- Recommandations

### Task 10 - Clôture (5 min)
- Vérifier l'absence de données sensibles
- Remplir `checklist_fin.md`

## 📚 Références OWASP

| Catégorie | Description |
|-----------|-------------|
| MASVS-STORAGE | Stockage des données |
| MASVS-CRYPTO | Cryptographie |
| MASVS-AUTH | Authentification |
| MASVS-NETWORK | Communications |
| MASVS-PLATFORM | Plateforme |
| MASVS-CODE | Qualité du code |
