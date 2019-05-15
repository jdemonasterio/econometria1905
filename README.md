# econometria1905
Curso Econometria - W. Sosa Escudero Mayo 2019


# Setting the env 

Just install `pipenv` tool in your local machine, see [this guide](https://github.com/pypa/pipenv#installation) for more info on that.

After that, you'll use the `Pipfile` at the root of this repo to install all ncessary python files via doing:

`cd /this-repo`
then `pipenv install --dev --skip-lock`

This operation will install important packages for this repo such as 
```
- jupyter
- nbconvert
- jupyter-contrib-nbextensions
```
Also the following 2 packages, which lets us export `.ipynbs` files to pdfs via latex.
You'll have to have Latex installed in your environment, so see how to do that in the following guides:
https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/install.html
https://nbconvert.readthedocs.io/en/latest/install.html

# Converting .ipynbs into pdfs
From this [guide](https://nbconvert.readthedocs.io/en/latest/usage.html) the idea is to run the command
`jupyter nbconvert --to pdf your_file.ipynb`
and have the output pdf be returned to the local directory.

## Removing all code cells
Following this [stackoverflow answer](https://stackoverflow.com/questions/31517194/how-to-hide-one-specific-cell-input-or-output-in-ipython-notebook)

`jupyter nbconvert --TemplateExporter.exclude_code_cell=True --to pdf Tercer_TP.ipynb`

## Tagging specific cells to remove them completely (input/output)
https://stackoverflow.com/questions/31517194/how-to-hide-one-specific-cell-input-or-output-in-ipython-notebook

You'll have to launch the jupyter hub via `jupyter notebook` and then select the `Nbextensions` menu at the top middle.
Inside you'll see the option `Cell filter` which let's one add "tags" (keywords) to cells.

Later we'll launch the `.ipynb` file and select from the top-menu: `View > Cell Toolbar > Tags`.
Each cell will now have a Tags toolbar where we'll be able to add the `"remove_cell"` tag.

Finally after selecting cells and adding the tag, we  *save the .ipynb file*, then run:
`jupyter nbconvert --TagRemovePreprocessor.remove_cell_tags='{"remove_cell"}' --to pdf Tercer_TP_tagged.ipynb`
to get a nice .pdf without the removed cells :)