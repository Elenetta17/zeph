# 🌬️ Zeph

[![GitHub license](https://img.shields.io/github/license/dioptra-io/zeph)](https://github.com/dioptra-io/zeph/blob/main/LICENSE)
[![PyPI](https://img.shields.io/pypi/v/dioptra-zeph?color=blue&logo=pypi&logoColor=white)](https://pypi.org/project/dioptra-zeph/)

> Zeph is a reinforcement learning based algorithm for selecting prefixes to probe based on previous measurement in order to maximize the overall discoveries of nodes and links. Zeph can be used on top of [Iris](https://iris.dioptra.io) system.


## 🚀 Quickstart

Zeph dispose of a command line interface to configure and run the algorithm.

Fist create the python virtual environment:

```
poetry install 
```

Then, you can run the script: `python -m zeph`:

```
Usage: zeph.py [OPTIONS]

Options:
  --api-url TEXT                  [default: https://api.iris.dioptra.io]
  --api-username TEXT             [required]
  --api-password TEXT             [required]
  --database-url TEXT             [default:
                                  http://localhost:8123?database=iris]

  --bgp-prefixes-path PATH        [required]
  --agent-tag TEXT                [default: all]
  --tool TEXT                     [default: diamond-miner]
  --protocol TEXT                 [default: icmp]
  --min-ttl INTEGER               [default: 2]
  --max-ttl INTEGER               [default: 32]
  --epsilon FLOAT                 [default: 0.1]
  --previous-measurement-uuid UUID
  --fixed-budget INTEGER
  --dry-run / --no-dry-run        [default: False]
  --install-completion [bash|zsh|fish|powershell|pwsh]
                                  Install completion for the specified shell.
  --show-completion [bash|zsh|fish|powershell|pwsh]
                                  Show completion for the specified shell, to
                                  copy it or customize the installation.

  --help                          Show this message and exit.
```

## ✨ Generate the BGP prefix file 

To work, Zeph needs to know the universe of BGP prefixes that it can probe. 
You can create a BGP prefix file by downloading the latest rib from routeviews.org and then convert it into a pickle file.

The easiest way to do that is to use the command line tools from located in `utils/` folder.

### Download RIB

Script: `poetry run zeph-bgp-download`

```
Usage: zeph_bgp_download.py [OPTIONS]

Options:
  --latestv4 / --no-latestv4      [default: False]
  --latestv6 / --no-latestv6      [default: False]
  --filepath PATH
  --install-completion [bash|zsh|fish|powershell|pwsh]
                                  Install completion for the specified shell.
  --show-completion [bash|zsh|fish|powershell|pwsh]
                                  Show completion for the specified shell, to
                                  copy it or customize the installation.

  --help                          Show this message and exit.
  ```

### Convert the RIB to pickle file

Script: `poetry run zeph-bgp-convert`

```
Usage: zeph_bgp_convert.py [OPTIONS] ROUTEVIEWS_FILEPATH

Arguments:
  ROUTEVIEWS_FILEPATH  [required]

Options:
  --bgp-prefixes-path PATH
  --excluded-prefixes-path PATH
  --install-completion [bash|zsh|fish|powershell|pwsh]
                                  Install completion for the specified shell.
  --show-completion [bash|zsh|fish|powershell|pwsh]
                                  Show completion for the specified shell, to
                                  copy it or customize the installation.

  --help                          Show this message and exit.
```



## 📚 Publications

```
```

## 🧑‍💻 Authors

Iris is developed and maintained by the [Dioptra group](https://dioptra.io) at [Sorbonne Université](https://www.sorbonne-universite.fr) in Paris, France.
