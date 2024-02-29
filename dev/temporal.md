Temporal Insights
=================

Initial Setup (Python)
----------------------

```
mkdir my-temporal
cd my-temporal
python3 -m venv env
source env/bin/activate
python -m pip install temporalio
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
