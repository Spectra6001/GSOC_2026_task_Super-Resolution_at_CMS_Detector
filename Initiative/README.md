# Super Resolution using Diffusion Model
This repository contains the implementation of a custom Denoising Diffusion Probabilistic Model (DDPM) designed specifically for the super-resolution of high-energy physics calorimeter data. The model maps low-resolution energy deposits to 125×125 high-resolution detector geometries while strictly adhering to underlying physical laws.
## Objective of the Initiative
This initiative is taken to get a better understanding of architectural stability, identify potential training bottlenecks and validate physics informed loss integration with diffusion model before scaling it to the full framework.
## Implementation Details
### Data Engineering & Representation
- **Log Transformation:** To stabilize the forward diffusion process and variance schedules, the raw energy values are log-transformed prior to adding Gaussian noise:  $E′=log_{10}​(E+1)$.
- **Inverse Transformation:** During the reverse sampling phase, all model outputs are inversely transformed back to the physical linear scale $(E=10^{E^′}−1)$ before calculating physical benchmark metrics or physics-informed losses.
### Diffusion Architecture
