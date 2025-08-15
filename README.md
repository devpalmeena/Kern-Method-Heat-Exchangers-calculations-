# Recursive Method for Heat Transfer Coefficient Calculation

## Overview
This repository implements a recursive numerical method for determining the overall heat transfer coefficient (U) in heat exchangers, particularly useful when dealing with complex geometries or variable properties.

## Method Description
The recursive approach iteratively refines the heat transfer coefficient calculation by:
1. Initial estimation of U based on empirical correlations
2. Calculating heat transfer rates and temperature distributions
3. Updating fluid properties based on local temperatures
4. Recalculating individual heat transfer coefficients (h₁, h₂)
5. Computing new overall coefficient: `1/U = 1/h₁ + R_fouling + t_wall/k_wall + 1/h₂`
6. Repeating until convergence (|U_new - U_old| < tolerance)

## Key Features
- **Convergence Control**: Adaptive tolerance and maximum iteration limits
- **Property Updates**: Temperature-dependent fluid properties (viscosity, thermal conductivity, Prandtl number)
- **Multiple Geometries**: Shell-and-tube, plate, and finned-tube heat exchangers
- **Fouling Factors**: Accounts for fouling resistance in calculations

## Algorithm Flow
```
Initial Guess → Property Evaluation → Heat Transfer Coefficients → 
Overall U Calculation → Convergence Check → Update/Iterate
```

## Applications
- Shell-and-tube heat exchangers
- Plate heat exchangers  
- Air-cooled heat exchangers
- Condensers and evaporators

## Advantages
- **Accuracy**: Accounts for temperature-dependent properties
- **Stability**: Controlled convergence prevents oscillations
- **Flexibility**: Adaptable to various heat exchanger types
- **Physical Realism**: Captures coupling between heat transfer and fluid properties

## Usage
The recursive method is particularly valuable when:
- Large temperature differences exist across the exchanger
- Fluid properties vary significantly with temperature
- High accuracy is required for design optimization
- Iterative design processes are involved

## Implementation Notes
- Typically converges within 5-15 iterations
- Under-relaxation factors (0.1-0.5) may be needed for stability
- Initial guess quality affects convergence speed
- Monitor for physical consistency in results
