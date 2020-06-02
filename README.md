# GPS-utilities
This repository contains a series of jupyter notebooks to postprocess GPS data. Each notebook is oragnized within a folder, where also example files are stored.

## PPP + PPK Processing of EMLID Reach RS+ GPS data
This script can be used to process data from two EMLID REACH RS+ GPS receivers (single band). One is a rover, the second is used as base station. Base station data are processed with PPP. To use the script, the following inputs are required:
 - Base station data processed with the National Resources Canada (NRCAN) Precise Point Positioning service (CSRS-PPP)
 - Rover data processed with RTKlib as kinematic points and saved as *.pos* file
 - Files exported from the data collector in *.csv* format
