# edaviz
edaviz - Python library for Exploratory Data Analysis and Visualization in Jupyter Notebook or Jupyter Lab

> Beta Version: edaviz is currently in active beta development and we update the library weekly. If you find an error, please report it to us.

- [Installation](#Installation)
- [Usage](#Usage)
- [API](#API)

# Installation

Currently, we are in private beta testing mode. You will receive the initial `pip install` command directly from us when you have been chosen for early access.

## After the pip install:
In addition, you need to activate extensions for Jupyter Lab or Jupyter Notebook:

### if you use Jupyter Notebook

```
jupyter nbextension enable --py widgetsnbextension
jupyter nbextension enable --py qgrid
```

### if you use Jupyter Lab

> Important: Jupyter Lab extensions require that you have nodejs installed on your computer.
<a href="https://jupyterlab.readthedocs.io/en/stable/user/extensions.html#installing-extensions" target="_blank">Official install guide for Jupyter Lab Extensions</a>


```
jupyter labextension install @jupyter-widgets/jupyterlab-manager --no-build
jupyter labextension install plotlywidget@0.8.0 --no-build
jupyter labextension install @jupyterlab/plotly-extension@0.18.2 --no-build
jupyter labextension install jupyterlab-chart-editor@1.0 --no-build
jupyter labextension install qgrid --no-build
jupyter lab build
```


# Usage

Execute the following code in a Jupyter cell:
```
import edaviz as eda
df = eda.get_titanic_df()  # sample pandas dataframe
eda.overview(df)
```
> Info: currently, edaviz only works within Jupyter Notebook or Jupyter Lab. You cannot use it on other platforms, e.g. via the command line or in PyCharm etc

# API

You will be able to discover most of the library functions via the `eda.overview(df)` widget.
Later, we will provide a full overview of all functions here.

## 3 most important functions:
- `eda.overview(df)` shows an overview widget of a given dataframe. This is the main entry point of the edaviz library
- `eda.plot(df, column_1, column_2)` shows a suitable bivariate plot of the two columns, e.g. `eda.plot(df, "Survived", "Age")`. The big advantage is that you do not have to specify the chart type because a best practice visualization is inferred based on the column data types
- `eda.patterns(df)` answers the question: _"between which columns exist predictive patterns?"_


## Advanced API
In addition, you might want to try the following functions:
- `eda.preview(df)` creates an interactive preview of the dataframe
- `eda.compare_subset(df, df_subset)` shows a comparison overview similar to the `eda.crossfilter(df)`. The only difference is that you can specify the filtered subset via `df_subset`, e.g. via `df_subset = df[df.Survived >= 1)]`



