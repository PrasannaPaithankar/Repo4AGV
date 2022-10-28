# Power System Architecture for Eklavya IGVC 2023
### 🧑🏻‍🦱 Prasanna Paithankar 
#### 💻 Department of Computer Science & Engineering, IIT Kharagpur
***
Repository intended to organize Task documents regarding IGVC 2023
## Battery Pack Selection & Modelling
1. Would be employing Li-ion battery pack.
2. Dual Polarization model will be used for analysis

## Battery Management System
#### SoC Determination & Protection Circuitry

The work has been done for AGV Selection Task: [AGV-Embedded-Task](https://github.com/PrasannaPaithankar/AGV-Embedded-Task)

#### Cell Balancing

We look into the following
* [Overview of cell balancing methods for Li-ion batterytechnology](https://www.researchgate.net/publication/343643135_Overview_of_Cell_Balancing_Methods_for_Li-ion_Battery_Technology)
* [Cell Balancing With the bq77PL900](https://www.ti.com/lit/an/slua463/slua463.pdf)
* [Passive Cell Balancing of Li-Ion batteries used for Automotive Applications](https://iopscience.iop.org/article/10.1088/1742-6596/1716/1/012005/pdf)

#### Temperature monitoring

General temperature sensor IC's to be usedd to monitor battery pack with suitable Bang Bang controller for the response during charging and discharging
## Power Distribution 
The following voltages and their prospective power requirments have been proposed
* 24V/210W - Motors
* 12V/30W - FlashLight, Lidar
* 9V/5W - No known subscriber
* 5V/10W - General logic Level
* 3.3V/5W - General logic level 
  
We propose two general architectures
* 24V Battery 
  - 12V would be stepped down using good conversion system
  - General embedded IC's to be used for other voltage levels
* Two 12V Batteries in series
  - Would serve to nearly eliminate losses involved during 24V to 12V conversion
  
In the above we can always include battery packs in parallel to increase capacity

## Circuit schematic for cell balancing
<img src="https://github.com/PrasannaPaithankar/Repo4AGV/blob/main/IGVC-2023/Screenshot%20(1076).png" class="bg-primary" width="250px">

***
##### Regarding Autonomous Ground Vehical Research Group, IIT Kharagpur
<img src="https://github.com/PrasannaPaithankar/AGV-Embedded-Task/blob/main/V_oc-vs-SoC-Determination/AGVlogo.png" class="bg-primary" width="150px">
