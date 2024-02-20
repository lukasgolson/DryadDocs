# Scenario Configuration



Dryad runs simulations across a combined set of configurations called "scenarios". Each scenario is made up of two parts,
a fixed configuration that is static across the scenarios and a dynamic scenario specific configuration.

Scenarios are defined in the `Scenarios.json` file found in the root of the simulation project.

The fixed part of the configuration looks like the following. Here you can define the number of steps the simulation will take,
the seed, and the species composition of mean-value (non inventory) simulation runs. 

> When the seed is set to `0`, a random seed will be generated for each new simulation run. 
> The seed will be identical across all scenarios during the run.
>
> {style="note"}

```JSON
 {
    "NumberOfSteps": 20,
    "Seed": 0,
    "SpeciesComposition": [
      {
        "Genus": "GenusName",
        "Species": "speciesName",
        "Ratio": 0.5
      },
      {
        "Genus": "GenusName2",
        "Species": "speciesName2",
        "Ratio": 0.5
      }    
  ]
}
```

The following default `Scenarios.json` is generated if the file does not exist when running a new simulation.
```JSON 
```
{src="Scenarios.json"}

