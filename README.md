# Host Jupyter Book on ReadtheDocs

This is the Jupyter Book sample hosted on ReadtheDocs

Setting up the `.readthedocs.yaml` can be tricky if you are doing it for the first time.
This can get your Jupyter Book hosted ReadtheDocs out-of-the-box.
In the example below, the name of the book is `jbtest`. Check out the repo for the structure.


```yaml
# .readthedocs.yaml
# Read the Docs configuration file
# See https://docs.readthedocs.io/en/stable/config-file/v2.html for details

# Required
version: 2

# Set the version of Python and other tools you might need
build:
  os: ubuntu-20.04
  tools:
    python: "3.8"
  jobs:
    pre_build:
      # Generate the Sphinx configuration for this Jupyter Book so it builds.
      - "jupyter-book config sphinx jbtest/"

python:
  install:
    - requirements: jbtest/requirements.txt

sphinx:
  builder: html
  fail_on_warning: true

```