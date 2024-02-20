# Model Formulas

All the formulas used in the simulation are configurable across three levels. Root (generic), Genus, and Species.

Formulas are defined in a file called `formulas.json` at the root of the simulation project. 

Sub-ranks override properties from parent ranks. In cases where a formula is not defined in any rank, the formula will resolve as the
constant `0`. At each rank, you can define the name (top level name should be `root` or left undefined, 
followed by the genus name at the second level, and species name at the third level).



Rank Definition Example:
```JSON
{
  "Name": "Rank Name",
  "Config": {
    "CarbonRatioFormula": "0",
    "VolumeFormula": "0",
    "DensityFormula": "0",
    "TreeGrowthFormula": "0",
    "BaseMortalityRateFormula": "0",
    "InfectionRateFormula": "0"
  },
  "SubRank": []
}

```



The following default `formulas.json` is generated if the file does not exist when running a new simulation.
```JSON
{
  "Config": {
    "CarbonRatioFormula": "0.5",
    "VolumeFormula": "0",
    "DensityFormula": "0.5",
    "TreeGrowthFormula": "DBH + 2.5",
    "BaseMortalityRateFormula": "0.1",
    "InfectionRateFormula": "0.02"
  },
  "SubRank": [
    {
      "Name": "Acer",
      "Config": {
        "CarbonRatioFormula": "0.5",
        "VolumeFormula": "0",
        "DensityFormula": "0.5",
        "TreeGrowthFormula": "DBH + 2.5",
        "BaseMortalityRateFormula": "0.1",
        "InfectionRateFormula": "0.02"
      },
      "SubRank": [
        {
          "Name": "rubrum",
          "Config": {
            "CarbonRatioFormula": "0.5",
            "VolumeFormula": "0",
            "DensityFormula": "0.5",
            "TreeGrowthFormula": "DBH + 2.5",
            "BaseMortalityRateFormula": "0.1",
            "InfectionRateFormula": "0.02"
          }
        }
      ]
    }
  ]
}

```