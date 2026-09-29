## Install env

Create the environnement 3.1X :
`py -3.1X -m venv .venv`

`.venv\Scripts\activate`

Check the version with `python --version`

Set the file "settings.json" in the `.vscode` directory:
```
{
    "python-envs.defaultEnvManager": "ms-python.python:venv",
    "python-envs.defaultPackageManager": "ms-python.python:pip",
}
```

## Package installation

run `pip install -r install-requirements.txt`

## Run the notebook 

Select the env kernel in the notebook, if not available :
run `python -m ipykernel install --user --name myproject --display-name "Python (.venv)"`