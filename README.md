# GPS-utilities
This repository contains a series of jupyter notebooks to postprocess GPS data. Each notebook is oragnized within a folder, where also example files are stored.

## Single GNSS position from multiple points
This script usess a Monte-Carlo approach to calculate the average position (with positioning uncertainties) given a series of GNSS points collected at the same location. It can be used, for example, when several processing options are available for a base station point.


## PPP + PPK Processing of EMLID Reach RS+ GPS data
This script can be used to process data from two EMLID REACH RS+ GPS receivers (single band). One is a rover, the second is used as base station. Base station data are processed with PPP. To use the script, the following inputs are required:
 - Base station data processed with the National Resources Canada (NRCAN) Precise Point Positioning service (CSRS-PPP)
 - Rover data processed with RTKlib as kinematic points and saved as *.pos* file
 - Files exported from the data collector in *.csv* format
