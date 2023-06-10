Python Insights
=================

IDE
---

* Love (PyCharm by JetBrains)[https://www.jetbrains.com/pycharm/]

Important libraries
-------------------

* Mongodb: https://github.com/mongodb/mongo-python-driver
* PDF: (ReportLab) https://bitbucket.org/rptlab/reportlab
* Websockets: pip install websockets
* pyyaml: pip install pyyaml

Setting up barebones use case tests
-----------------------------------

```
class InvoiceTests(unittest.TestCase):
  def setUp(self):
        pass

  def test_something(self):
        self.assertFalse(...)
```
