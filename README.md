# ai-music-recommender
Hybrid AI music recommendation system using CNN, content filtering, collaborative filtering, sequential learning, and reinforcement learning.

## Datasets

All datasets should live in the `datasets/` folder (on .gitignore so never committed)

### Music4All (48 GB)

Request access from the [Music4All website](https://sites.google.com/view/contact4music4all), then extract the archive to `datasets/music4all` if the folders doesn't exist yet.

### Music4All-Onion (15 GB)

Run [download_music4all_onion.ipynb](download_music4all_onion.ipynb). It automatically downloads the files we use from [Zenodo](https://zenodo.org/records/15394646) and extracts them to `datasets/music4all-onion`:

- `userid_trackid_count`, `userid_trackid_timestamp`
- `id_musicnn`, `id_mfcc_stats`, `id_essentia`
- `id_genres_tf-idf`, `id_tags_dict`

It also downloads the dataset's own `README.md`, which describes every feature file.

(`userid_trackid_timestamp.tsv` is ~11 GB; set `INCLUDE_TIMESTAMPS = False` in the notebook to skip it).
