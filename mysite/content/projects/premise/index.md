---
title: "PREMISE"
date: 2022-12-20T15:11:59+01:00
startdate: 2019-09-20
draft: false
description: "Interfacing the ecoinvent lca inventory database and IAM scenarios."
image: "premise.png"
giturl: "https://github.com/polca/premise"
languages: "Python"
technologies: "Brightway2, Wurst, Pandas, Numpy, Scipy"
---

<img style="width: 200px;" class="img-fluid rounded float-end me-3" src="premise.png">
From the [documentation](https://premise.readthedocs.io/en/latest/):

> premise allows to align the life cycle inventories contained in the ecoinvent 3 cutoff database with the output results of Integrated Assessment Models (IAM), such as REMIND or IMAGE, in order to produce life cycle inventory databases under future policy scenarios for any year between 2005 and 2100.

The first version of this software has been developed by Brian Cox at PSI who wrote an extensive 
monolithic function as part of a jupyter notebook. I extended and systemized the code into the python
package `rmnd-lca`. Since 2021, [Romain Sacchi](https://github.com/polca/premise/commits?author=romainsacchi) almost solely contributed to the codebase.




