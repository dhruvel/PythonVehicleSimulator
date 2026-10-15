# Python Vehicle Simulator

The Python Vehicle Simulator supplements the MATLAB MSS (Marine Systems Simulator) Toolbox. It includes models for autonomous underwater vehicles (AUVs), unmanned surface vehicles (USVs), and ships. The vehicle models are based on the MSS vessel models in /MSS/VESSELS/catalog. Each vehicle is modeled as an object in Python, and the vehicle class has methods for guidance, navigation, and control. The main program ```main.py``` defines vehicle objects for real-time simulation. 

    Root folder:
    /src/python_vehicle_simulator/ 
        main.py                 - MAIN PROGRAM (terminal command >> python3 main.py)
        3D_animation.gif        - 3D animation file that can be opened in a web browser by right-clicking the file   
        
    Library files:
    /src/python_vehicle_simulator/lib/         
        control.py              - feedback control systems
        gnc.py                  - generic GNC functions
        guidance.py             - guidance functions        
        mainLoop.py             - main simulation loop
        plotTimeSeries.py       - plotting and animation functions

    Vehicle classes/methods: 
    /src/python_vehicle_simulator/vehicles/              
        DSRV.py                 - Deep submergence rescue vehicle (DSRV) controlled by a stern plane, L = 5.0 m
        frigate.py              - Frigate, rudder-controlled ship described by a nonlinear Nomoto model, L = 100.0 m
        otter.py                - Otter unmanned surface vehicle (USV) controlled by two propellers, L = 2.0 m
        ROVzefakkel.py          - Zeefakkel, rudder-controlled ship described by a nonlinear Nomoto model, L = 54.0 m
        semisub.py              - Semisubmersible controlled by tunnel thrusters and main propellers, L = 84.5 m
        shipClarke83.py         - Ship, linear maneuvering model specified by L, B and T using the Clarke (1983) formulas
        supply.py               - Offshore supply vessel controlled by tunnel thrusters and main propellers, L = 76.2 m
        tanker.py               - Tanker, rudder-controlled ship model including shallow water effects, L = 304.8 m
        remus100.py             - Cylinder-shaped AUV controlled by a rudder, stern planes and a propeller, L = 1.6 m 
        torpedo.py              - Cylinder-shaped torpedo controlled by a rudder, stern planes and a propeller, L = 1.6 m         
        
For more information about the mathematical modeling of marine craft and methods for guidance, navigation, and control, please consult:

T. I. Fossen (2021). Handbook of Marine Craft Hydrodynamics and Motion Control. 2nd. Edition, Wiley. 
https://wiley.fossen.biz

## Install
From the repository root, install the project and its development dependencies with:

```sh
uv sync --group dev
```

Run the interactive simulator with:

```sh
uv run python -m python_vehicle_simulator.main
```

Run the test suite with:

```sh
uv run pytest
```
