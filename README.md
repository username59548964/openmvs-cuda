# OpenMVS avec CUDA pour toutes les cartes NVIDIA

Compilation automatique (GitHub Actions) d'[OpenMVS](https://github.com/cdcseacave/openMVS)
**2.4.0**, sources officielles inchangées, avec CUDA pour toutes les générations de
cartes NVIDIA :

| Génération | Cartes |
|---|---|
| sm_61 Pascal | GTX 10xx |
| sm_70 Volta | Titan V |
| sm_75 Turing | GTX 16xx, RTX 20xx |
| sm_80, sm_86 Ampere | A100, RTX 30xx, RTX A-series |
| sm_89 Ada | RTX 40xx |
| sm_90 Hopper | H100 |
| sm_100 Blackwell | B200 |
| sm_120 Blackwell | RTX 50xx (bureau et portable), RTX PRO Blackwell |
| PTX compute_120 | cartes futures (recompilé par le pilote) |

Pourquoi : la version Windows officielle (`OpenMVS_Windows_x64_CUDA.7z`) est compilée
avec `CMAKE_CUDA_ARCHITECTURES=native`, donc seulement pour la carte de la machine qui
l'a compilée (sm_89, RTX 40) ; sur une autre carte, le nuage dense échoue.

Résultats : onglet *Releases* (Windows x64 en `.zip`, Linux x86_64 en `.tar.xz`,
empreintes SHA-256). Pilote NVIDIA 570 ou plus récent.

Licence : OpenMVS est sous AGPL-3.0 ; les sources sont celles du dépôt officiel au
commit indiqué dans `.github/workflows/compiler.yml` ; ce fichier de compilation est
sous la même licence.
