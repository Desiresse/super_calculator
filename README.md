
# SuperCalculator

SuperCalculator est une application de calculatrice avancée écrite en Go, capable d'effectuer des opérations mathématiques de base et intégrée dans un pipeline CI/CD complet.

## Fonctionnalités

- **Addition** : Ajoutez deux nombres.
- **Soustraction** : Soustrayez un nombre d'un autre.
- **Multiplication** : Multipliez deux nombres.
- **Division** : Divisez un nombre par un autre.
- **Tests unitaires** : Le projet inclut des tests unitaires pour garantir la qualité du code.

## Workflows GitHub Actions

Ce projet inclut plusieurs workflows pour répondre aux besoins des développeurs :

1. **Workflow de publication :**
   - Compile le projet avec GoReleaser.
   - Génère des images Docker et les publie sur Docker Hub.

2. **Workflow de lint :**
   - Exécute une analyse statique avec Semgrep.
   - Analyse le fichier Docker avec Hadolint.
   - Exécute Super-Linter pour valider les modifications (pull request uniquement).

3. **Workflow de test :**
   - Exécute les tests unitaires sur les versions 1.17, 1.18 et 1.19 de Go.

4. **Gestion des dépendances :**
   - Dépendabot est configuré pour surveiller les dépendances Go et Docker quotidiennement.

## Instructions d'installation

1. Clonez ce dépôt :
   ```bash
   git clone https://github.com/<votre-utilisateur>/<nom-du-dépôt>.git
   cd <nom-du-dépôt>
   ```

2. Installez les dépendances :
   ```bash
   go mod tidy
   ```

3. Exécutez l'application :
   ```bash
   go run main.go
   ```

4. Lancez les tests unitaires :
   ```bash
   go test ./...
   ```

## Configuration Docker

Pour construire et pousser une image Docker :
1. Configurez vos identifiants Docker Hub comme secrets dans GitHub Actions :
   - `DOCKERHUB_USERNAME`
   - `DOCKERHUB_TOKEN`

2. Build et push l'image manuellement :
   ```bash
   docker build -t <votre-utilisateur>/supercalculator:latest .
   docker push <votre-utilisateur>/supercalculator:latest
   ```

## Contribution

Les contributions sont les bienvenues. Veuillez ouvrir une issue ou soumettre une pull request si vous souhaitez améliorer le projet.

---

### Auteur

Projet réalisé dans le cadre de la mise en œuvre de workflows CI/CD pour SuperCalculator.
