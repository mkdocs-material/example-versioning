> This is an example of the new [versioning][1] feature of
[Material for MkDocs][2].

  [1]: https://squidfunk.github.io/mkdocs-material/setup/setting-up-versioning/
  [2]: https://squidfunk.github.io/mkdocs-material/

## How to set up versioning

First, install [Material for MkDocs Insiders][3] and [mike][4]:

```
pip install git+https://${GH_TOKEN}@github.com/squidfunk/mkdocs-material-insiders.git
pip install mike
```

  [3]: https://squidfunk.github.io/mkdocs-material/insiders/
  [4]: https://github.com/jimporter/mike

Next, set up your documentation project:

```
mkdocs new .
```

Update `mkdocs.yml`:

``` yaml
site_name: My Docs
theme:
  name: material
extra:
  version:
    method: mike
```

Make a change to `docs/index.md`, and publish the first version:

```
mike --push --update-aliases 0.1 latest
```

Set the default version to `latest`

```
mike set-default --push latest
```

Now, make another change and publish a new version:

```
mike --push --update-aliases 0.2 latest
```
