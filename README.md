# melodi <a href="https://pole-odl.gitlab-pages.insee.fr/melodi/"><img src="man/figures/logo.png" align="right" height="139" alt="melodi website" /></a>

Package facilitant l'utilisation des données et métadonnées diffusé par l'Insee via [Melodi](https://catalogue-donnees.insee.fr)

## Installation

Installer la dernière version stable depuis github :
```R
# install.packages("remotes")
remotes::install_github("cbobinec/melodi", build_vignettes = TRUE)
```

Installer la dernière version stable en interne Insee :
```R
install.packages("melodi", repos = "https://nexus.insee.fr/repository/r-public/")
```

## Exemples

Lister les jeux de données proposés par l'Insee via Melodi :
```R
get_catalog()
```

Récupérer toutes les données d'un jeu de données par son identifiant :
```R
data <- get_all_data("DS_POPULATIONS_REFERENCE")
```

## Configuration

### Authentification et quota de requêtes
Le package repose sur l'API Melodi, accessible sans authentification.

Son usage est limité à **30 requêtes par minute** : au delà, un code réponse **429** est obtenu.

### Proxy

Dans le cas d'une utilisation du package depuis un réseau d'entreprise, il peut être utile de configurer le proxy d'accès internet de la manière suivante :

```R
Sys.setenv(http_proxy = "my_proxy_server:port")
Sys.setenv(https_proxy = "my_proxy_server:port"")
# Désactiver le proxy sur certaines adresses
#Sys.setenv(no_proxy = "exemple-url-interne.server.fr")
```
