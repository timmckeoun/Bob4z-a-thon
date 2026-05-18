# Lab : Skill Bob Premium for Z - Génération et Validation COBOL

## Objectif

Ce lab démontre l'utilisation du skill **Bob Premium for Z** pour générer des programmes COBOL conformes aux standards IBM Enterprise COBOL pour z/OS avec CICS, puis valider automatiquement la syntaxe avec Z Open Editor.

## Prérequis

- VS Code avec Z Open Editor installé
- Workspace CBSA ouvert
- Skill `cobol-generator-validator` disponible dans `.bob/skills/`

## Création du Skill

### Demande

```text
Crée un skill Bob Premium for Z, à l'aide du skill builder, qui permet de générer un programme COBOL puis de vérifier à l'aide de Z Open Editor, la syntaxe et le standard du COBOL généré. Les erreurs de syntaxe devront être corrigées par Bob.
```
### Résultat

Bob va utiliser le skill `coding-standards-skill-builder` pour créer le skill `cobol-generator-validator` dans `.bob/skills/` avec :
- `skill.yaml` : configuration du skill
- `skill.py` : logique de génération et validation
- `templates/` : modèles de code COBOL
- `requirements.txt` : dépendances


## Activation du Skill

Le skill s'active automatiquement avec ces phrases :
- "Génère un programme COBOL"
- "Crée un COBOL"
- "Valide COBOL"
- "Bob Premium for Z"

## Exemple 1 : Génération d'un Programme Simple

### Demande

```
Génère un programme COBOL qui permette de trouver le compte d'un client à partir de son numéro de téléphone
```

### Résultat Attendu

Bob va :

1. **Analyser les besoins du programme de recherche par téléphone**
2. **Vérifier la structure du copybook CUSTOMER pour le champ téléphone**
3. **Générer le programme COBOL conforme aux standards IBM**
4. **Valider avec Z Open Editor**
5. **Corriger les erreurs détectées**



## Exemple 2 : Programme CICS avec BMS Map

### Demande

```
Crée un programme COBOL avec Bob Premium for Z qui utilise une map BMS 
pour afficher et mettre à jour des informations de compte bancaire.
Le programme doit s'appeler UPDTACCT et utiliser un pattern pseudo-conversationnel.
```

### Résultat Attendu

Bob génère un programme complet avec :
- Pattern pseudo-conversationnel (COMMAREA)
- Gestion des maps BMS (SEND/RECEIVE)
- Validation des entrées utilisateur
- Gestion d'erreur MAPFAIL
- Structure DISPLAY-MODE et UPDATE-MODE

## Standards Appliqués

### 1. Directives de Compilation

**CICS Standard :**
```cobol
PROCESS CICS,NODYNAM,NSYMBOL(NATIONAL),TRUNC(STD)
CBL CICS('SP,EDF')
```

**CICS + DB2 :**
```cobol
PROCESS CICS,NODYNAM,NSYMBOL(NATIONAL),TRUNC(STD)
CBL CICS('SP,EDF')
CBL SQL
```

**CICS + DLI :**
```cobol
PROCESS CICS,NODYNAM,NSYMBOL(NATIONAL),TRUNC(STD)
CBL CICS('SP,EDF,DLI')
```

### 2. Conventions de Nommage

| Élément | Convention | Exemple |
|---------|-----------|---------|
| Variables WS | `WS-` + descriptif | `WS-CUSTOMER-ID` |
| Paragraphes | Verbe + objet | `PROCESS-CUSTOMER-RECORD` |
| Condition names | État descriptif | `VALID-CUSTOMER` |
| Constantes | Majuscules + tirets | `MAX-RECORDS` |

### 3. Gestion d'Erreur CICS

**Pattern Obligatoire :**
```cobol
EXEC CICS [COMMAND]
    [PARAMETERS]
    RESP(WS-CICS-RESP)
    RESP2(WS-CICS-RESP2)
END-EXEC.

IF WS-CICS-RESP NOT = DFHRESP(NORMAL)
    MOVE '[OPERATION]' TO WS-ERROR-OPERATION
    PERFORM HANDLE-CICS-ERROR
END-IF.
```



## Conclusion

Le skill **Bob Premium for Z** automatise complètement le processus de génération et validation de programmes COBOL conformes aux standards IBM Enterprise COBOL pour z/OS avec CICS.

**Avantages clés :**
- ✅ Génération automatique conforme aux standards
- ✅ Validation avec Z Open Editor
- ✅ Correction automatique des erreurs
- ✅ Documentation complète
- ✅ Code prêt pour la production

**Pour commencer :**
Dites simplement "Génère un programme COBOL avec Bob Premium for Z" et suivez les instructions !

---

**Version** : 1.0.0  
**Date** : 2026-05-12  
**Auteur** : Bob for Z Team
