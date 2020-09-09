# CoVee Control
# Coordinated Voltage Control


## Download the respository
please clone it with: git clone --recursive <ssh-link>  (to download the submodules) 
The submodule installed in the "dmu", a tool to REST API

## Installation

# to populate the containers with a virtual environment
- run in terminal: make all

# There are three containers:
- pv_centralized: Run the voltage control
- powerflow:  Run the powerflow (simulation of the electrical grid)
- grafana (optional):  For the visualization


# Running pv_centralized and powerflow containers:
- There is a docker-compose.yml file, that is installing all the required components for each container.
- run in terminal: sudo docker-compose up

# Running grafana container:
- There is a different docker-container-grafana.yml
- run in terminal: sudo docker-compose -f docker-container-grafana.yml up

# There is a python file to test external message to the voltage control (to control the number of active nodes):
- run in terminal: make ext
- This generate a virtual environment to run: PF_conf_inputs.py
- The code simply generate a json message that is posted via REST API


# To remove the virtual environments:
- run in terminal: make clean
- run in terminal: make clean_ext