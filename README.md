# Remaining Usefull Life Estimator

## Description
Prognostics and health management is an important topic in industry for predicting state of assets to avoid downtime and failures. This data set is the Kaggle version of the very well known public data set for asset degradation modeling from NASA. It includes Run-to-Failure simulated data from turbo fan jet engines.

Engine degradation simulation was carried out using C-MAPSS. Four different were sets simulated under different combinations of operational conditions and fault modes. Records several sensor channels to characterize fault evolution. The data set was provided by the Prognostics CoE at NASA Ames.

## Prediction Goal

In this dataset the goal is to predict the remaining useful life (RUL) of each engine in the test dataset. RUL is equivalent of number of flights remained for the engine after the last datapoint in the test dataset. 

## Turbofan Engine

<img src="https://github.com/ameyak2310/TurboFanEngine_RUL-Estimator/blob/main/References/TurboFancrossSection.png?raw=true" width="200">

![Turbofan Cross-section](https://github.com/ameyak2310/TurboFanEngine_RUL-Estimator/blob/main/References/TurboFancrossSection.png?raw=true)

## Jet propulsion Cycle
![Jet Propulsion Cycle](https://github.com/ameyak2310/TurboFanEngine_RUL-Estimator/blob/main/References/JetPropulsionCycle.png?raw=true)

## Data Set 
Ref : 

#### Experimental Scenario
Data sets consists of multiple multivariate time series. Each data set is further divided into training and test subsets. Each time series is from a different engine i.e., the data can be considered to be from a fleet of engines of the same type. Each engine starts with different degrees of initial wear and manufacturing variation which is unknown to the user. This wear and variation is considered normal, i.e., it is not considered a fault condition. There are three operational settings that have a substantial effect on engine performance. These settings are also included in the data. The data is contaminated with sensor noise.

The engine is operating normally at the start of each time series, and develops a fault at some point during the series. In the training set, the fault grows in magnitude until system failure. In the test set, the time series ends some time prior to system failure. The objective of the competition is to predict the number of remaining operational cycles before failure in the test set, i.e., the number of operational cycles after the last cycle that the engine will continue to operate. Also provided a vector of true Remaining Useful Life (RUL) values for the test data.

The data are provided as a zip-compressed text file with 26 columns of numbers, separated by spaces. Each row is a snapshot of data taken during a single operational cycle, each column is a different variable. The columns correspond to:

|   Sr.   No.    |    Column   Names    |                Data                |    Units   |
|:--------------:|:---------------------|:-----------------------------------|:----------:|
|        1       | unit_number          | Unit Number                        |      --    |
|        2       | time_in_cycles       |  Cycle number                      |      --    |
|        3       | setting_1            | Altitude                           |      ft    |
|        4       | setting_2            |  Mach Number                       |      --    |
|        5       | TRA                  |  Throttle resolver angle           |   degrees  |
|        6       | T2                   |  Total temperature at fan   inlet  |    deg R   |
|        7       | T24                  |  Total temperature at LPC   inlet  |    deg R   |
|        8       | T30                  |  Total temperature at HPC   inlet  |    deg R   |
|        9       | T50                  |  Total temperature at LPT   inlet  |    deg R   |
|       10       | P2                   |  Pressure at fan inlet             |     psia   |
|       11       | P15                  |  Total pressure in bypass-duct     |     psia   |
|       12       | P30                  |  Total pressure at HPC outlet      |     psia   |
|       13       | Nf                   |  Physical fan speed                |     rpm    |
|       14       | Nc                   |  Physical core speed               |     rpm    |
|       15       | epr                  |  Engine pressure ratio   (P50/P2)  |      --    |
|       16       | Ps30                 |  Static pressure at HPC outlet     |     psia   |
|       17       | phi                  |  Ratio of fuel flow to Ps30        |   pps/psia |
|       18       | NRf                  |  Corrected fan speed               |     rpm    |
|       19       | NRc                  |  Corrected core speed              |     rpm    |
|       20       | BPR                  |  Bypass Ratio                      |      --    |
|       21       | farB                 |  Burner fuel-air ratio             |      --    |
|       22       | htBleed              |  Bleed Enthalpy                    |      --    |
|       23       | Nf_dmd               |  Demanded fan speed                |     rpm    |
|       24       | PCNfR_dmd            |  Demanded corrected fan speed      |     rpm    |
|       25       | W31                  |  HPT Coolant Bleed                 |    lbm/s   |
|       26       | W32                  |  LPT Coolant Bleed                 |    lbm/s   |

#### Operating Conditions

|   Data set     |   Train Trajectory   |   Test Trajectory    |    Conditions   |    Fault Modes                       |
|:--------------:|:---------------------|:---------------------|:----------------|--------------------------------------|
|    FD001       | 100                  | 100                  | One (Sealevel)  |ONE (HPC Degradation)                 |
|    FD002       | 260                  | 259                  | SIX             |ONE (HPC Degradation)                 |
|    FD003       | 100                  | 100                  | One (Sealevel)  |TWO (HPC Degradation, Fan Degradation)|
|    FD004       | 248                  | 249                  | SIX             |TWO (HPC Degradation, Fan Degradation)|


## Reference:
1. A. Saxena, K. Goebel, D. Simon, and N. Eklund, ‘Damage Propagation Modeling for Aircraft Engine Run-to-Failure Simulation’, in the Proceedings of the 1st International Conference on Prognostics and Health Management (PHM08), Denver CO, Oct 2008.
2. D. Frederick, J. DeCastro, and J. Litt, "User’s Guide for the Commercial Modular Aero-Propulsion System Simulation (C- MAPSS)," NASA/ARL, Technical Manual TM2007-215026, 2007.
3. NASA's Open Data Portal (https://www.nasa.gov/content/diagnostics-prognostics)
