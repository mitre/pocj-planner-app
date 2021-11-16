# PoCj Planner App
PoCj Planner App is a is a space traffic visualization tool that uses a satellite file to calculate the risk of RSOs conjuncting at various altitudes.

The Probability of Conjunction Planning Tool (PoCjPlanner) is a high-level space traffic visualization tool that uses a satellite file (e.g., TLE, 3LE, RSO spreadsheet, etc.) to calculate the probability of conjunction (PoCj) for any given resident space object (RSO) at various altitude bands.

This tool is not intended to be used operationaly, but rather for first-order mission planning, and visualization of object density at different altitudes around Earth. When used as intended, the tool can provide a picture of how crowded an orbit is, and thus inform alternate orbit designs or potential risk.

PoCj is a statistical metric used here to characterize the probability of an RSO falling within a user defined keep-out-volume of another object within a user defined altitude band. For example, defining a 2x25x25km box keep-out cell for an object with a 417x422km altitude orbit will characterize the same screening criteria used for the ISS.

The user is required to provide the Satellite File and specify the input criteria (Keep-out Cell size, Keep-out Cell Shape, Perigee altitude, Apogee Altitude, and Altitude Band Interval). The Satellite File can be downloaded from space-track.org as a standard TLE or 3LE element set. Alternatively, the user can provide a custom-made spreadsheet, so long as the spreadsheet contains a row of headers with one of the following two orbit characteristic pairs:

- “Apogee” & “Perigee”
- “Eccentricity” & “Mean Motion” (or “Ecc” & “MM”)

One of the above orbit characteristic pairs are required in the spreadsheet headers with spelling accuracy, or the tool will not be able to calculate. The utility of using a spreadsheet is that it can be for a “future” catalog and provide insights to the density of objects in the future (e.g. once all Mega Constellations on file are operational)

Compatible File Formats:

- .txt
- satf
- TLE
- 3LE
- .csv
- .xlsx (not recommended due to loading time)
- .xlsb (not recommended due to loading time)
- .xls (not recommended due to loading time)

.txt, satf, TLE, and 3LE all have the fastest run times. .csv is the recommended form of spreadsheet to be used as it will run the fastest. .xlsx, .xlsb, and .xls are compatible, but are not recommended due to very long load times. 

Once a satellite file is loaded and the input criteria defined, the user only needs to hit calculate for the tool to operate. It will provide 2 tables in the UI as outputs. The PoCj across all Altitude Bands (AB) will display the number of objects in each altitude band, the PoCj, the Odds of conjunction, and the Estimated number of conjunctions occurring in the respective altitude band.

The PoCj across User Specified AB table will provide the PoCj for the user specified Perigee-Apogee orbit altitudes, the odds of conjunction across the orbit the percentage of the catalog that crosses the specified orbit, and the estimated number of conjunctions across the orbit.

Once calculation is complete, the user may use the Export Table button to save the results as a spreadsheet, or the Plot button to see the PoCj across all orbits, PoCj in LEO, and the Estimated Number of Conjunctions across all orbits.

After initial calculation, the raw satellite file data is stored for quicker calculation on subsequent runs. This allows the user to modify the input criteria and re-run the tool without waiting for file loading times on each run.
