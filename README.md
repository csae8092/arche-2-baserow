# ARCHE Constants Metadata Creator

This Repository is used to create Baserow tables for creating ARCHE Metadata.
It creates the following tables:

* Classes (All available vocabs:ARCHE classes like: Project, TopCollection, Collection, etc.)
* Properties (All available vocabs:ARCHE properties like: hasTitle, hasDescription, etc.)
* Vocabs (All available vocabularies from [vocabs.acdh.oeaw.ac.at](https://vocabs.acdh.oeaw.ac.at).)
* Project (A table linked to all other tables for creating ARCHE constants project metadata.)
* Persons (A table for creating ARCHE constants person metadata.)
* Organizations (A table for creating ARCHE constants organization metadata.)
* Places (A table for creating ARCHE constants places metadata.)

## Usage (Github Actions)

* Login to Baserow and create a new workspace for a project.
* Then [create a new API token in Baserow](https://baserow.io/user-docs/personal-api-tokens).
* Clone this repository and either delete the `.git` folder and initialize new git repo or change the origin to your needs; you can also fork the repo.
add the API token to the [secrets of the Github repository](https://docs.github.com/en/codespaces/managing-codespaces-for-your-organization/managing-development-environment-secrets-for-your-repository-or-organization) as `BASEROW_TOKEN`. Add more secrets for the user as `BASEROW_USER` and password as `BASEROW_PW`.
* [Trigger the workflow manually](https://docs.github.com/en/actions/using-workflows/manually-running-a-workflow) and add the Baserow Datebase ID of the database in your Baserow workspace in the required Github Actions Input field.

## Installation and Usage (Local)

make sure you set `BASEROW_TOKEN`, `BASEROW_USER` and `BASEROW_PW` as environment variables

```bash
python -m venv venv # create a virtual environment
source venv/bin/activate # activate the virtual environment

pip install -r requirements.txt # install python dependencies

python scripts/arche2json.py # create json files from ARCHE Schema
python scripts/vocabs2json.py # create json files from vocabs.acdh.oeaw.ac.at
python scripts/arche2baserow.py # upload json files to baserow to create tables
```
