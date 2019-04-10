# edaviz
edaviz - Python library for Exploratory Data Analysis and Visualization in Jupyter Notebook or Jupyter Lab

- [Installation](#Installation)
- [Usage](#Usage)
- [API](#API)

# Installation

Currently, we are in private beta testing mode. You will receive the initial `pip install` command directly from us when you have been chosen for early access.

## After the pip install:
In addition, some of the widgets need to be activated in Jupyter Lab or Jupyter Notebook depending on your setup:

### with Jupyter Notebook

```
jupyter nbextension enable --py widgetsnbextension
jupyter nbextension enable --py qgrid
```

### with Jupyter Lab (requires npm)

```
jupyter labextension install @jupyter-widgets/jupyterlab-manager --no-build
jupyter labextension install plotlywidget@0.8.0 --no-build
jupyter labextension install @jupyterlab/plotly-extension@0.18.2 --no-build
jupyter labextension install jupyterlab-chart-editor@1.0 --no-build
jupyter labextension install qgrid --no-build
jupyter lab build
```


# Usage

```
import pandas as pd
df = pd.read_csv("titanic.csv")  # read any CSV file

import edaviz as eda
eda.overview(df)
```


# API

You will be able to discover most of the library functions via the `eda.overview(df)` widget.
Later, we will provide a full overview of all functions here.

## Advanced API
In addition, you might want to try the following functions:
- `eda.preview(df)` creates an interactive preview of the dataframe
- `eda.compare_subset(df, df_subset)` shows a comparison overview similar to the `eda.crossfilter(df)`. The only difference is that you can specify the filtered subset via `df_subset`, e.g. via `df_subset = df[df.Survived >= 1)]`



