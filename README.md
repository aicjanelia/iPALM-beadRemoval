# iPALM Bead Removal
Beads are automatically removed from iPALM data by first finding the beads in the total raw data and then filtering the localization list to remove localizations near a bead location.

The current version of this code is in [src/Python](src/Python/). A now deprecated MATLAB version is also available in [scr/MATLAB](src/MATLAB/).

## Overview
Bead removal requires a fully processed PeakSelector `.sav` file. Make sure any channel alignment, filtering, purging, etc. is complete.  The current Python version reads the `.sav` file directly and does not need the data exported in a different format.

See [the Python README](src/Python/README.md) for details on environment set up and parameter setting for the bead removal Jupyter notebook. Make sure to review the generated figures for accurate bead removal before proceeding with downstream analysis. The final output of the notebook is a CSV file containing the localization data. This file can be reloaded into PeakSelector (as described below) or analyzed in other programs. Please note that x and y coordinates are described in pixels (133.33 nm/pixel) while z is described in nm.

## Using txt files with PeakSelector
The output txt files can be reloaded into PeakSelctor through the menu option _Import User ASCII_ by choosing xy coords in pixels, checking the box for headers, and inputting the values 0 to 48 for the data columns (see the file _peakSelector_columnIndices_ for an easy list of values to copy and paste).
