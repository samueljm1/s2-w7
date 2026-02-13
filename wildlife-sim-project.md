# Wildlife Population Simulator

## Project Overview
A simulation program that models wildlife population dynamics using real-world species data and biological parameters. Students read CSV files, use 1D arrays to store and manage data, and write simulation results back to CSV.

## Learning Objectives
- **File I/O**: Read and write CSV files using `Scanner` and `PrintWriter`
- **1D Arrays**: Use parallel arrays to store object-related data (species names, populations, rates, etc.)
- **Data Processing**: Parse CSV data, validate inputs, and transform data
- **Algorithm Design**: Implement population simulation logic with birth/death rates and carrying capacity

## Real Data Sources
Species data is based on actual conservation estimates:
- **African Elephants**: ~415,000 (IUCN Red List 2024)
- **Black Rhinos**: ~6,000 (critically endangered, down from thousands)
- **Giant Pandas**: ~1,864 (conservation success story)
- **Grizzly Bears**: ~1,000 (North American recovery program)
- **Sumatran Tigers**: ~400 (one of most endangered)
- **Mountain Gorillas**: ~1,000 (intensive conservation efforts)

Birth and death rates are based on published ecological research.

## Project Files

### Data Files
- **species-data.csv**: Initial population data with birth/death rates
- **simulation-results.csv**: Output file with final populations

### Java Classes
1. **WildlifeSimulator.java**: Core simulation engine using 1D arrays
   - Parallel arrays for species names, populations, rates, etc.
   - Simulation logic (births, deaths, capacity limits)
   - Analysis methods (total population, most endangered, etc.)


2. **WildlifeSimulatorRunner.java**: Main program
   - Orchestrates the simulation
   - Displays results and statistics

## Data Structure
Uses parallel 1D arrays (all same length):
```java
Species[] species
```

## Population Simulation Formula
For each year, for each species:
```
births = population × birthRate
deaths = population × deathRate
newPopulation = (population + births - deaths)

// Apply habitat capacity limit
if (newPopulation > habitatCapacity)
    newPopulation = habitatCapacity

// Prevent negative populations
if (newPopulation < 0)
    newPopulation = 0
```


## Extension Ideas
1. **ArrayList Version**: Replace arrays with ArrayLists for dynamic sizing
2. **User Interaction**: Let students input parameters or choose simulation length
3. **Predator-Prey Model**: Add interactions between species
4. **Extinction Risk**: Calculate probability of species extinction
5. **Multiple Scenarios**: Compare simulations with different climate/habitat changes
6. **Data Visualization**: Export to format for charting population trends
7. **File Validation**: Add error checking for malformed CSV data

## CSV Format

**Input (species-data.csv):**
```
species,population,birthRate,deathRate,habitatCapacity,location
African Elephant,415000,0.06,0.04,500000,Africa
Black Rhino,6000,0.03,0.05,15000,Africa
...
```

**Output (simulation-results.csv):**
```
species,population,birthRate,deathRate,location
African Elephant,447362,0.06,0.04,Africa
Black Rhino,5123,0.03,0.05,Africa
...
```

## Teaching Notes
- This project reinforces **file I/O** which pairs well with your City Population Analyzer
- Demonstrates real-world applications of arrays in scientific simulation
- Data validation is implicit (malformed lines are skipped)
- Birth/death rates show how small percentages compound over time
- Habitat capacity introduces conditional logic (max function)
