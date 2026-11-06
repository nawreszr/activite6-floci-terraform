# Activité 6 : Cloud Local (Floci), Terraform, et Automatisation

## 📖 Description
Ce dépôt regroupe les réponses et les manipulations réalisées pour l'Activité 6, couvrant :
- L'utilisation de **Floci** (émulateur AWS local) pour simuler S3, SQS, DynamoDB, Lambda et Secrets Manager.
- L'introduction à **Terraform** pour provisionner de l'infrastructure sur Floci.
- Les concepts avancés de **Terraform** (modules, workspaces, backend distant, analyse de sécurité).
- L'automatisation avec **Terraform + Ansible**.

---

## 📂 Contenu du Dépôt
- `README.md` : Ce fichier (documentation des tâches).
- `floci/` : Fichiers de configuration Docker et scripts liés à Floci.
- `terraform/` : Configuration Terraform (providers, modules, environnements).
- `ansible/` : Playbooks Ansible pour la configuration.
- `captures/` : Captures d'écran prouvant les résultats.

---

## 📝 Réalisation des Tâches

### 22. Cloud local avec Floci

- [ ] **106** : Installer Floci en conteneur Docker et le démarrer.
  *Commande :* `docker run -d --name floci -p 4566:4566 floci/floci`
  *Preuve :* À faire (capture de `docker ps`).

- [ ] **107** : Configurer AWS CLI pour Floci.
  *Commandes :* `aws configure --profile floci` puis `aws --profile floci --endpoint-url http://localhost:4566 sts get-caller-identity`

- [ ] **108** : Créer un bucket S3 local avec AWS CLI.
  *Commande :* `aws --profile floci --endpoint-url http://localhost:4566 s3 mb s3://mon-bucket-local`

- [ ] **109** : Envoyer un fichier dans le bucket S3 puis le récupérer.

- [ ] **110** : Créer une file SQS locale, envoyer un message et le lire.

- [ ] **111** : Créer une table DynamoDB locale et ajouter des données.

- [ ] **112** : Créer une fonction Lambda locale (Node.js) et l'invoquer.

- [ ] **113** : Stocker une valeur dans Secrets Manager local.

- [ ] **114** : Faire communiquer une API Express avec Floci (SQS / S3).
  *À faire :* Schéma de l'architecture et capture du résultat.

- [ ] **115** : Ajouter Floci dans un fichier `docker-compose.yml`.

- [ ] **116** : Utiliser Floci dans un pipeline GitHub Actions (tests d'intégration).

- [ ] **117** : Comparer Floci, LocalStack et AWS réel (licence, services, fidélité, coût, CI).

---

### 23. Introduction à Terraform

- [ ] **118** : Installer Terraform et vérifier avec `terraform version`.

- [ ] **119** : Créer un projet Terraform (`providers.tf`, `main.tf`, `variables.tf`, `outputs.tf`) configuré pour Floci.

- [ ] **120** : Exécuter `terraform init`, `fmt`, `validate`, `plan`.

- [ ] **121** : Créer automatiquement S3, SQS et DynamoDB via Terraform.

- [ ] **122** : Vérifier avec AWS CLI que Terraform a bien créé les ressources.

- [ ] **123** : Détruire les ressources avec `terraform destroy`.

---

### 24. Terraform avancé

- [ ] **124** : Transformer la configuration en modules réutilisables.

- [ ] **125** : Créer des configurations séparées pour `dev`, `staging` et `prod`.

- [ ] **126** : Expliquer le rôle du fichier Terraform State.

- [ ] **127** : Configurer un backend distant S3 hébergé dans Floci.

- [ ] **128** : Activer le verrouillage du state et vérifier le blocage d'une exécution simultanée.

- [ ] **129** : Ajouter Checkov ou Trivy IaC au pipeline CI.

- [ ] **130** : Introduire volontairement une mauvaise configuration (bucket public) et vérifier que le pipeline échoue.

- [ ] **131** : Tester OpenTofu avec la même infrastructure et comparer avec Terraform.

- [ ] **132** : Utiliser Terragrunt pour factoriser DEV/STAGING/PROD.

- [ ] **133** : Découvrir Pulumi en recréant une ressource Floci (TypeScript ou Python).

---

### 25. Automatisation Terraform + Ansible

- [ ] **134** : Utiliser Terraform pour créer l'infrastructure et Ansible pour la configurer.

- [ ] **135** : Supprimer et reconstruire toute l'infrastructure via les scripts.
