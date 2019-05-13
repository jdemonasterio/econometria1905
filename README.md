# econometria1905
Curso Econometria - W. Sosa Escudero Mayo 2019


# Setting the env 

Just install `pipenv` tool in your local machine, see [this guide](https://github.com/pypa/pipenv#installation) for more info on that.

After that, you'll use the `Pipfile` at the root of this repo to install all ncessary python files via doing:

`cd /this-repo`
then `pipenv install --dev --skip-lock`

This operation will install important packages for this repo such as 

Also the following 2 packages, which lets us export `.ipynbs` files to pdfs via latex.
You'll have to have Latex installed in your environment, so see how to do that in the following guide:

https://nbconvert.readthedocs.io/en/latest/install.html
https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/install.html

# Converting .ipynbs into pdfs
From this [guide](https://nbconvert.readthedocs.io/en/latest/usage.html) the idea is to run the command
`jupyter nbconvert --to pdf your_file.ipynb`
and have the output pdf be returned to the local directory.


## Removing all code cells
Following this [stackoverflow answer](https://stackoverflow.com/questions/31517194/how-to-hide-one-specific-cell-input-or-output-in-ipython-notebook)

`jupyter nbconvert --TemplateExporter.exclude_code_cell=True --to pdf Tercer_TP.ipynb`
