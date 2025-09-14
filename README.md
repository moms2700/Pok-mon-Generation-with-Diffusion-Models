# 🎮 Pokémon Diffusion Model - Génération d'Images avec Deep Learning

## 📋 Description du Projet

Ce projet implémente un système de génération d'images de Pokémon utilisant des modèles de diffusion (DDPM - Denoising Diffusion Probabilistic Models). Le système utilise une architecture U-Net conditionnée par des embeddings textuels CLIP pour générer des images de Pokémon à partir de descriptions textuelles incluant leur nom et leurs types.

## 🚀 Caractéristiques Principales

- **Web Scraping Automatisé** : Collecte automatique des images et métadonnées de Pokémon depuis Bulbapedia
- **Modèle de Diffusion Conditionnel** : Génération d'images basée sur des embeddings textuels CLIP
- **Architecture U-Net Optimisée** : Implémentation personnalisée avec connexions résiduelles et attention
- **Visualisation en Temps Réel** : Suivi du processus de génération étape par étape
- **Support GPU** : Optimisation complète pour l'entraînement sur GPU

## 📊 Évolution du Projet

Le projet présente trois implémentations successives avec des améliorations progressives :

### Version 1 - Implémentation Initiale
- Architecture basique avec problèmes de mémoire
- Images 128x128, résultats très bruités
- Temps d'entraînement : >24h

### Version 2 - Optimisations
- Réduction à 32x32 pixels pour efficacité
- Meilleure gestion mémoire
- Temps d'entraînement : 12h

### Version 3 - Implémentation Finale ✅
- Architecture U-Net améliorée
- Visualisation du processus de diffusion
- Temps d'entraînement : 6h
- Résultats de qualité significativement supérieure

## 🛠️ Technologies Utilisées

- **TensorFlow/Keras** : Framework de deep learning
- **CLIP (OpenAI)** : Génération d'embeddings textuels
- **BeautifulSoup** : Web scraping
- **NumPy/OpenCV** : Traitement d'images
- **Matplotlib** : Visualisation

## 📁 Structure du Projet

```
pokemon-diffusion/
├── data_collection/
│   ├── scraper.py          # Web scraping depuis Bulbapedia
│   └── preprocessor.py     # Traitement et embeddings CLIP
├── models/
│   ├── unet.py            # Architecture U-Net
│   ├── diffusion.py       # Processus DDPM
│   └── training.py        # Boucle d'entraînement
├── generation/
│   └── sampler.py         # Génération d'images
├── pokemon_images/        # Images collectées
├── embeddings/           # Embeddings CLIP
└── results/             # Images générées
```

## 🚦 Installation et Utilisation

```bash
# Cloner le repository
git clone https://github.com/[username]/pokemon-diffusion.git
cd pokemon-diffusion

# Installer les dépendances
pip install -r requirements.txt

# Collecter les données
python data_collection/scraper.py

# Entraîner le modèle
python models/training.py

# Générer des Pokémon
python generation/sampler.py --name "Charizard" --types "Fire,Flying"
```

## 📈 Performances

| Métrique | Version Finale |
|----------|---------------|
| Résolution | 32x32 pixels |
| Temps d'entraînement | ~6 heures |
| Mémoire GPU | 2-4GB |
| Vitesse de génération | <5 secondes |
| Dataset | ~900 Pokémon |

## 🎯 Résultats

Le modèle est capable de générer des images reconnaissables de Pokémon avec :
- Formes cohérentes selon les types
- Couleurs appropriées
- Structures caractéristiques des Pokémon

## ⚠️ Limitations

- Résolution limitée à 32x32 pixels
- Détails fins parfois manquants
- Dataset relativement petit (~900 images)
- L'approche avec encodeur latent (4ème tentative) s'est révélée moins efficace

## 🔮 Améliorations Futures

- [ ] Augmenter la résolution des images générées
- [ ] Implémenter des mécanismes d'attention plus sophistiqués
- [ ] Explorer l'augmentation de données pour enrichir le dataset
- [ ] Optimiser l'architecture pour des images 64x64 ou 128x128
- [ ] Ajouter un système de contrôle plus fin (pose, expression, etc.)

## 📚 Apprentissages Clés

Ce projet démontre que :
1. La simplicité architecturale peut surpasser la complexité dans les modèles de diffusion
2. La préservation de la dimensionnalité est cruciale pour la qualité
3. L'approche directe sur les pixels est plus efficace que l'utilisation d'espaces latents pour des datasets limités

## 🤝 Contribution

Les contributions sont les bienvenues ! N'hésitez pas à :
- Signaler des bugs
- Proposer des améliorations
- Soumettre des pull requests

## 📄 Licence

Ce projet est à des fins éducatives et de recherche uniquement.
