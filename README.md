# Kerbal Space Program manoeuvre node executor for Principia
## Updated March 2025

My node executor script for space manoeuvres in Kerbal Space Program, intended to be used with [the Principia n-Body gravitation mod](https://github.com/mockingbirdnest/Principia).
Tested in KSP 1.12.3 with a full RSS/RO install and Principia

# Installation

You will find one folder: 
- **Ships/Script**

Put the contents of the folder inside Ship/Script so that kOS can see all the files.

# Usage
- The script to be run is **node.ks**
- The script will exit immediately if there is no manoeuvre node to execute
- The script will automatically measure the engine parameters of any ship you call it from
- If no engines are sensed, the script will downmode to using RCS. It will assume that there are RCS thrusters along the ship main axis and it will not do any performance calculations
- The script executes just a single node
- The script assumes that there is enough propellant to make the burn, and will not take care of propellant stability or other RSS stuff

# How it works

The script measures the requested delta-V and the senses delta-V change during the burn. When enough delta-V has been accumulated, the burn is complete. The delta-V is measured factoring out the dV change due to gravity alone.  

The tangent, radial and binormal components of the burn unit vector are kept constant as the burn progresses. This means that the direction unit vector itself is not constant, but rotates along with the unit trihedron as the burn goes. I did it this way because it's how Principia simulates the burn.

# Accuracy results
WIP
