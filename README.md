# Machine-Learning-Battery-SOC-Estimaton-Electric-Vehicles


This repository contains the codes to implement a data driven framework to predict the state-of-charge (SOC) of Lithium-Ion Batteries in Electric Vehicles applications. The codes provided in this repository have been developed as part of a project about Machine Learning applied to Lithium-Ion Batteries research at the University of Illinois at Chicago. The results illustrated in this repository have contributed to the paper "Data driven estimation of electric vehicle battery state-of-charge informed by automotive simulations and multi-physics modeling" published in the Journal of Powe Sources in 2020. 
#  Matlab codes-Electric Vehicle Simulation

Matlab and Simulink are used to perform Electric Vehicle simulation. The dynamic EV model is built in Simulink usig the Power Train Blockset modules, which allows to simulate the component of the vehicles such as the battery pack, the electric motor, the differential etc. through appropriate blocks parametrized using lookup tables. In order to create the lookup tables needed by the Simulink EV model we need to run Matlab scripts. The scripts are implemented for two EV, TeslaS and Nissan Leaf. The EV simulations are necessary to simulated the time series of the electro-mechanical variables used to train and test Machine Learning models to predict the State-Of-Charfe in electric vehicles applications.

# Battery Parametrization
One of the main difference between these two vehicles is the battery pack. **TeslaS** has a battery pack of **8256 cylindrical cells**, managed in a **96s86p series/parallel connection**. A single cell is characterized by a **C-NMC chemistry** (anode material: Carbon,  cathode material: Nickel-Manganese-Cobalt) and it has a nominal capacity of 2.86 Ah and a nominal voltage of 4.2 V, resulting in a total capacity of 246 Ah and total energy of 100 kWh. This type of battery allows TeslaS to achieve **a driving range of ~600 km** before recharging the battery.

On the other hand, **Nissan Leaf** has a battery pack of **288 pouch cells**, managed in a **96s3p series/parallel connection**. A single cell is characterized by a **C-LMO chemistry** (anode material: Carbon,  cathode material: Lithium-Manganese-Oxygen) and it has a nominal capacity of 56.3 Ah and a nominal voltage of 4.2 V, resulting in a total capacity of 169 Ah and total energy of 62 kWh. This type of battery allows TeslaS to achieve **a driving range of ~363 km** before recharging the battery.

These information are implemented in the EV model, through an appropriate parametrization of the battery module. The parametrization is built on top of dishcarge curves at constant C-rate at different temperatures and constant temperature at different C-rates, computed with a P2D model in COMSOL Multiphysics and saved in txt files. There scripts to perform the parametrization are in the folders **parametrization_steps_TeslaS** and **parametrization_steps_NissanLeaf**. The script *battery_parametrization.m* allows to run all of them in one shot. Please run in Matlab:




