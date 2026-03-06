# TP1 — Deep Learning avec TensorFlow/Keras

## 📌 Description

Ce TP a pour objectif de développer un modèle d’apprentissage profond pour prédire le prix des maisons à partir du dataset **Ames Housing** en utilisant **TensorFlow et Keras**.

Le travail consiste à :

* Prétraiter les données
* Gérer les valeurs manquantes
* Encoder les variables catégorielles
* Standardiser les données
* Construire et entraîner un modèle de **Deep Learning**
* Évaluer les performances du modèle

---

# 📂 Dataset

Le dataset utilisé est **Ames Housing Dataset**.

Il contient des informations détaillées sur des maisons vendues dans la ville de **Ames (Iowa, USA)**.

### Variable cible

* **SalePrice** : prix de vente de la maison

### Types de variables

* Variables **numériques** : surface, nombre de pièces, année de construction, etc.
* Variables **catégorielles** : quartier, type de zone, etc.

---

# ⚙️ Prétraitement des données

Plusieurs étapes de nettoyage et de préparation des données ont été réalisées :

### 1️⃣ Gestion des valeurs manquantes

* Les colonnes avec beaucoup de valeurs manquantes ont été supprimées.
* Les variables numériques ont été remplacées par **la moyenne**.
* Les variables catégorielles ont été remplacées par **le mode**.

### 2️⃣ Encodage des variables catégorielles

Les variables catégorielles ont été transformées en variables numériques avec :

```python
pd.get_dummies()
```

### 3️⃣ Séparation des données

Le dataset a été séparé en :

* **80 % données d’entraînement**
* **20 % données de test**

### 4️⃣ Standardisation

Les variables ont été standardisées pour améliorer l’apprentissage du modèle.

---

# 🧠 Modèle de Deep Learning

Le modèle a été construit avec l’API **Keras Sequential**.

### Architecture du réseau

* Dense (128 neurones, ReLU)
* Dropout (0.3)
* Dense (128 neurones, ReLU)
* Dense (64 neurones, ReLU)
* Dense (32 neurones, ReLU)
* Dense (1 neurone — sortie)

### Optimiseur

Contrairement à l’exemple initial qui utilisait **RMSprop**, nous avons utilisé :

```
Adam
```

avec un learning rate de **0.001**.

### Fonction de perte

```
Mean Squared Error (MSE)
```

### Métrique

```
MAE (Mean Absolute Error)
```

---

# 🏋️ Entraînement du modèle

Le modèle a été entraîné avec :

* **100 epochs**
* **validation_split = 0.2**
* **batch_size = 32**

Cela permet d’observer l’évolution de l’erreur pendant l’entraînement et la validation.

---

# 📊 Résultats

Les graphiques montrent l’évolution de :

* **Training MAE**
* **Validation MAE**

On observe que :

* L’erreur diminue rapidement au début
* Le modèle converge progressivement
* Les performances se stabilisent autour de **17 000 – 20 000 MAE**

Cela indique que le modèle apprend correctement à prédire le prix des maisons.

---

# 📈 Améliorations apportées

Pour améliorer les résultats, plusieurs modifications ont été effectuées :

* Utilisation de l’optimiseur **Adam**
* Augmentation du nombre de **neurones**
* Ajout d’une couche **Dropout** pour éviter l’overfitting
* Augmentation du nombre d’**epochs**
* Utilisation d’un **batch_size** pour stabiliser l’apprentissage

---

# 🛠️ Technologies utilisées

* Python
* TensorFlow
* Keras
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

---

# 📁 Structure du projet

```
TP1-DeepLearning/
│
├── AmesHousing.csv
├── TP_1.ipynb
├── README.md
```

---

# 👨‍💻 Auteur

**EL MAHDI BOUDERNA**

Projet réalisé dans le cadre du **TP1 Deep Learning**.
