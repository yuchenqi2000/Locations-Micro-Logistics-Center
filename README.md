# Locations-Micro-Logistics-Center

## Introduction

I'm Yuchen Qi, a graduate of the Transport, Logistics, and Infrastructure master's program at TU Delft. I completed my master's thesis with the invaluable support of [Dr. Yousef Maknoon](https://www.tudelft.nl/en/staff/m.y.maknoon/?cHash=efb616eba407d0e740c43d2b6efc81b9), [Dr. Shadi Sharif Azadeh](https://www.tudelft.nl/staff/s.sharifazadeh/), and [Dr.ir. Gonçalo Correia](https://www.tudelft.nl/citg/over-faculteit/afdelingen/transport-planning/staff/persoonlijke-paginas/correia-g).

## Theme of the Research

This repository contains the code for my thesis titled **"[An Optimisation Approach to Planning Micro-logistics Centers for On-demand Food Delivery Service with A Mixed Operational Model](http://resolver.tudelft.nl/uuid:d8ecbe1a-4370-48ca-94fa-ccc77831312e)"** The research presents a comprehensive framework to assist on-demand meal delivery platforms in decision-making regarding delivery model choices and the planning of micro-logistics centers within a mixed operational model. 

We analyze two prevalent delivery models:
1. **Owner-Operator Model (IC)**: Operating with independent contractors.
2. **Company-Vehicle Model (CV)**: Utilizing micro-logistics centers that accommodate company-owned vehicles.

The goal is to determine the necessity of micro-logistics centers, indicating whether to maintain the IC model or adopt a hybrid approach, and to optimize the planning of these centers. We propose a mixed-integer optimization problem aimed at minimizing total costs while ensuring courier convenience. The framework combines strategic decisions regarding the location and dimensions of micro-logistics centers with operational considerations, including the distribution of couriers and shifts.

## Project Description

The project utilizes various instances to provide insights for platforms to choose different delivery models in varying markets. The simulation scenarios can be realized through the following steps:

### Step 1: Generate Data for Instances

Use the `generate_input_final.ipynb` notebook to generate the necessary data. The input data consists of several components, each generated in order and stored in pickle files. The relevant files for the model are:
- **NETWORK**: Information of an \( n \times n \) network.
- **S_T**: Number of couriers starting at each time.
- **probs_ST_random**: Spatial probability of couriers starting at each time.
- **S_I_T**: Number of couriers starting in each zone at each time (derived from S_T and probs_ST_random).
- **shift_probs**: Shift probability distribution.
- **des_probs**: Destination probability distribution.
- **E**: Ending distribution matrix (generated from S_I_T, shift_probs, and des_probs).

### Step 2: Optimization

The optimization models are implemented in `model_M_1.py` and `model_M_2.py`:

- **Model I**: Addresses a fixed-coverage problem with a return-to-origin operational policy. In this model, centers have fixed coverage areas for CV service, which remain constant over time, considering geographic connectivity constraints.
  
- **Model II**: Focuses on time-variant coverage and global redistribution optimization for more efficient resource allocation. This model allows for flexible coverage areas that can change over time and optimizes returns for CV couriers based on cost trade-offs.

### Accessibility Score Calculation

Due to business privacy concerns, we will only provide the code to calculate the accessibility score based on the Amsterdam public transport network.

## **Instructions**

1. **Clone the Repository**:
   ```bash
   git clone <repository_url>
   cd Locations-Micro-Logistics-Center
   
2. **Generate Data**:
Open and run the `generate_input_final.ipynb` notebook to generate the necessary input data.

3. **Run Optimization Models**:
Execute either `model_M_1.py` or `model_M_2.py` to perform the optimization based on your chosen model.

4. **Access Additional Files**:

- The complete thesis document can be found in `Thesis.pdf`.
- Visualizations related to the research are included in `Presentation.pptx`.

For further inquiries or issues, please feel free to reach out. Thank you for your interest in my research!
