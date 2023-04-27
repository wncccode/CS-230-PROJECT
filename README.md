# CS-230-PROJECT


```



The file explorer is accessible using the button in left corner of the navigation bar. You can create a new file by clicking the **New file** button in the file explorer. You can also create folders by clicking the **New folder** button.

##  Compile

All your files and folders are presented as a tree in the file explorer. You can switch from one to another by clicking a file in the tree.
```
$ ./build_champsim.sh bimodal no no no no lru 1
```
```
$ ./build_champsim.sh ${BRANCH} ${L1I_PREFETCHER} ${L1D_PREFETCHER} ${L2C_PREFETCHER} ${LLC_PREFETCHER} ${LLC_REPLACEMENT} ${NUM_CORE}
```

## Run simulation
```
Usage: ./run_champsim.sh [BINARY] [N_WARM] [N_SIM] [TRACE] [OPTION]
$ ./run_champsim.sh bimodal-no-no-no-no-lru-1core 1 10 400.perlbench-41B.champsimtrace.xz
```
```
${BINARY}: ChampSim binary compiled by "build_champsim.sh" (bimodal-no-no-lru-1core)
${N_WARM}: number of instructions for warmup (1 million)
${N_SIM}:  number of instructinos for detailed simulation (10 million)
${TRACE}: trace name (400.perlbench-41B.champsimtrace.xz)
${OPTION}: extra option for "-low_bandwidth" (src/main.cc)
```

## TAGE
In this project we've implemented TAGE predictor that won the CBP-4 championship. TAGE uses one bimodal table backed up with several tagged predictor components. Entries in the table are indexed using history lengths that form geometric series. There are multiple predictions and we will the best among these predictions as final prediction.
