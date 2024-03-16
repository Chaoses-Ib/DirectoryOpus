## Manual
Clone:
```sh
git clone https://github.com/Chaoses-Ib/DirectoryOpus.git
cd DO/source/private
```

Setup:
```sh
pip install -r ../requirements.txt
```
```sh
scoop install pandoc
```

Dump:
```sh
python -m dokuWikiDumper --current-only --ignore-disposition-header-missing --threads 3 --content --media --ignore-errors --path docs.dopus.com --force https://docs.dopus.com/doku.php
```
`--ignore-errors` is needed since the following links are broken:
- https://docs.dopus.com/doku.php?id=playground%3Aplayground
- https://docs.dopus.com/doku.php?id=wiki%3Adokuwiki
- https://docs.dopus.com/doku.php?id=wiki%3Asyntax
- https://docs.dopus.com/doku.php?id=wiki%3Awelcome

Convert: [manual.ipynb](manual.ipynb)

Move `media/media` and `media/release_history` to `Manual/images`.

RSS:
- Recent Changes: https://docs.dopus.com/feed.php
- https://docs.dopus.com/feed.php?mode=list&ns=