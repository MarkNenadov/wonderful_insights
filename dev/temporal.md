Temporal Insights
=================

Initial Setup (Python)
----------------------

```
mkdir my-temporal
cd my-temporal
python3 -m venv env
source env/bin/activate
python3 -m pip install temporalio
```

Setup Up Temporal Cluster
-------------------------

```
brew install temporal
curl -sSf https://temporal.download/cli.sh | sh
echo 'export PATH=$PATH:/Users/markn/.temporalio/bin' >> ~/.zshrc

```

Start Temporal Cluster
----------------------

```
temporal server start-dev
```

Verify it is listening to http://localhost:8233

You can change the port

```
temporal server start-dev --ui-port 8080
```

It defaults to an in-memory database, if you want a disk database, do this:

```
temporal server start-dev --db-filename your_temporal.db
```

Run The Samples
---------------

```
pip3 install poetry

git clone https://github.com/temporalio/samples-python.git
cd samples-python

poetry install
poetry run python hello/hello_activity.py
```
