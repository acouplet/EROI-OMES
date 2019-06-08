# EROI Optimisation Model for Energy Systems
This repository contains the `python` code for optimising the production capacity mix of Western Europe by minimising the net global **EROI**. This code is adapted from **Sylvain Ramelot** and **Thibault Martinelle**'s master thesis and initially inspired from the work of **Gauthier Limpens** in the article "*Electricity storage needs for the energy transition : an EROI based analysis illustrated for the case of Belgium*"

Contributors:
- Inspiration : **Gauthier Limpens** ([article](https://doi.org/10.1016/j.energy.2018.03.180))
- For the V1.0 : **Sylvain Ramelot** and **Thibault Martinelle** ([master thesis](http://hdl.handle.net/2078.1/thesis:14328))
- For the V2.0 : **Oscar de Giey** ([master_thesis](#)) and **Adrien Couplet** ([master_thesis](#))

## Getting Started
### Prerequisites
You need to have `python3` with `pip3` set up on your machine. Python can be downloaded from [this website](https://www.python.org/downloads/) and `pip3` can be installed by following [these instructions](https://pip.pypa.io/en/stable/installing/). 

Two solvers have been implemented in EROI-OMES:
- **COIN-OR CBC** solver, a free and open-source mixed integer programming solver
- (optional) **CPLEX** from IBM, a commercial mixed integer programming solver. An academic license can be obtained [here](https://ibm.onthehub.com/WebStore/OfferingDetails.aspx?o=4d1c8238-e141-e911-8113-000d3af41938) (Note: the *free/community* version is not the same as the *student* version and is not sufficient to run EROI-OMES) 

If you want to use EROI-OMES without contributing to the code, we suggest you download the latest version (V2.0) from the [releases](https://github.com/acouplet/EROI-OMES/releases/). On the other hand, if you want to contribute to this project, clone the git repository :
```
git clone https://github.com/acouplet/EROI-OMES
```

Some modules are needed to run the code. These are listed in `requirements.txt` and can be install using `pip3`:
```
pip3 install -r requirements.txt
```
(*Optional*) Users that want to use the **CPLEX** solver need to follow the [instructions](https://www.ibm.com/support/knowledgecenter/SSSA5P_12.6.2/ilog.odms.cplex.help/CPLEX/GettingStarted/topics/set_up/Python_setup.html) to setup the Python API of CPLEX. 
**Important**: do not install the cplex module through `pip3` as this will install the *free* (and thus limited) version of the Python API of CPLEX. 
The correct installation of the Python API of CPLEX can be verified with the following `python` commands:
```python
>>> import pulp
>>> pulp.pulpTestAll()
    ...
* Solver <class 'pulp.solvers.CPLEX_CMD'> passed.
    ...
```

You can obtain data for Western-Europe from [this location](https://uclouvain-my.sharepoint.com/:f:/g/personal/coupleta_oasis_uclouvain_be/EhJSfKLaRD9Du2zck0EnTb4Be8fQSux3UB3F9s4qM2vnaw?e=E3klrm). Just decompress the `.zip` archive inside the EROI-OMES directory.
