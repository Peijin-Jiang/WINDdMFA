# CAwindMFA
Canadian wind energy dynamic material flow analysis (dMFA)

This model presented a comprehensive analysis of capacity flow, material demand, EoL (end-of-life) management, and the environmental impact of material production for onshore wind turbines in Canada from 1993 to 2050 and offshore wind turbines from 2020 to 2050. The analysis examined four wind turbine components: foundation, nacelle, rotor, and tower. Several material types were covered in this study, including non-metal materials such as concrete and composites, metals (e.g.,steel, cast iron, copper (Cu), aluminum (Al)), and electrics/electronics (EE), as well as REEs in permanent magnets (e.g., neodymium (Nd) and dysprosium (Dy)). 

# How to Run the Project

## Prerequisites

- Python 3.11.9
- Git Bash (for Windows users)
- Required Python packages listed in `requirements.txt`

## Setup Instructions
### Clone the repository: Open a terminal (or Git Bash for Windows users) and run the following command to clone the project:

git clone https://github.com/Peijin-Jiang/CAwindMFA.git

cd CAwindMFA


### Use the following command to install the required Python packages:

pip install -r requirements.txt


### Once you're in the project directory, run the following command to execute all experiments:

bash run_all_experiments.sh


# Model Overview
![Alt text](model%20overview.png)

# Scenarios
- capacity flow: 2 energy demand scenarios (GCAM: Global Change Analysis Model and GNZ: Global Net Zero from Canada Energy Regulator)
- material demand: 2 energy demand scenarios * 3 tech devlopment scenarios (CT: conventional technology, AT: advanced technology, NT: new technology)
- material EoL: 2 energy demand scenarios * 3 tech devlopment scenarios * 2 EoL scenarios (EoL_C: current EoL treatment, EoL_O: optimistic EoL treatment)
- material production (cradle-to-gate) environmental impact: 2 energy demand scenarios * 3 tech devlopment scenarios * 2 EoL scenarios 

# Input data
## excel_path:str="input_data/Wind_data.xls"
- sheet_name='on_capacity': it includes two future onshore wind energy demand scenarios, onshore wind turbine capacity factor assumptions and average future onshore wind turbine capacity assumptions
- sheet_name='off_capacity': it includes two future offshore wind energy demand scenarios, offshore wind turbine capacity factor assumptions and average future offshore wind turbine capacity assumptions
- sheet_name='on_material': it contains the material composition of onshore wind turbines for each tech type of component
- sheet_name='off_material': it contains the material composition of offshore wind turbines for each tech type of component
- sheet_name='tech_dev': it contains three technology development scenarios (changes in nacelle market share, replacement rates of nacelles and rotors) for onshore and offshore wind turbines, it also contains the future lifetime assumption
- sheet_name='recy_rate_new': it contains two EoL scenarios for onshore and offshore wind turbine materials detailing the proportion allocated to five treatment methods
- sheet_name='envir_impact': it contains climate change impacts and energy consumption factors of materials used in wind turbines as well as the potential reduction factors in climate change impacts and energy consumption achievable through closed-loop recycling
- sheet_name='historical_info': it includes information on Canadian historical (from 1993-2019) 6,698 wind turbines' installation year, capacity, dimension size, component tech type, etc
- sheet_name='his_info2': Canadian historical wind turbine nacelle tech market share analysis
- sheet_name='his_analysis': it includes Canadian historical 28 years of wind turbine yearly average capacity, average rotor mass, and average nacelle mass

# Model Configuration

- **Future assumptions**: Parameters such as the average capacity per wind turbine, capacity factor, and lifetime, along with **future scenarios** like energy demand, technological development, and End-of-Life (EoL) treatment, can be modified in the provided Excel file. Once updated, the model can be re-run to reflect these changes.

- **Hardcoded parameters**: Certain parameters, including the wind turbine's Weibull shape factor, the regression results for the relationship between capacity and dimensions, and the relationship between dimensions and component mass, are hardcoded in the Python scripts. To modify these, you will need to manually update the relevant Python code.

