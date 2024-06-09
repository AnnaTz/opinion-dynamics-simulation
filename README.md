
This project was developed for the 'Data Programming in Python' course, part of the MSc in Data Analytics at the University of Glasgow in 2023. It presents a comprehensive simulation framework designed to explore the dynamics of opinion formation within communities. It models the interactions between individuals with varying stances on a given issue, leveraging spatial positioning and social networks to simulate opinion shifts over time. The simulation is implemented in Python, structured around a robust object-oriented design that prioritizes computational efficiency, especially critical for scenarios involving a significant number of individuals and/or time steps.

## Key Components

- **Class Definitions**:
  - `Individual`: Base class for all individual types. This class encapsulates the core functionalities and attributes common to all individuals in the simulation, including:
    - **Location**: The spatial coordinates (x, y) representing the individual's position.
    - **Opinion History**: A record of the individual's opinion changes over time.
    - **Contacts**: A list of other individuals that this person is connected to within the simulation.
    - **Update Method**: A method to update the individual's state based on the simulation's dynamics.
  - `UnbiasedIndividual`, `NegativeIndividual`, `PositiveIndividual`, `StubbornIndividual`: These classes inherit from `Individual`, each implementing specific behaviors and initial conditions reflecting their predisposition towards the issue at hand.
  - `Simulation`: The central class that orchestrates the simulation, incorporating methods to initialize the population, run the simulation, and generate outputs for analysis.

- **Key Features of the Simulation Class**:
  - `init`: Initializes the simulation with a set of parameters and creates the initial population.
  - `run`: Executes the simulation over a specified number of time steps.
  - `plot_network`: Visualizes the state of the population at a given time point, showing individuals' opinions and their connections.
  - `chart`: Generates a time series plot showing the evolution of opinion groups within the population.
  - `most_polarised`: Identifies the maximum polarization observed in the simulation.
  - `most_polarised_day`: Determines the day on which maximum polarization was observed.
  - `individual_summary`: Produces a detailed breakdown of each individual's opinion changes over time.
  - `friendship_similarity`: Assesses the opinion similarity among connected individuals.
  - `friendship_similarity_chart`: Charts the evolution of opinion similarity over time.
  - `ensemble_statistics`: Runs multiple simulation instances to analyze variability and statistical properties of the model outcomes.

- **Simulation Parameters**:
  - **T**: Number of simulated time steps.
  - **N**: Number of individuals in the simulation.
  - **αpos, αneg, αstub**: Probabilities that an individual is of the positive, negative, or stubborn type, respectively.
  - **γC, γop, γdist**: Parameters influencing the likelihood of connections based on spatial proximity and opinion similarity.
  - **βupdate, βspread**: Control the rate at which individuals' opinions change and the influence of differing opinions.
  - **γextr**: The probability that an individual becomes completely convinced (opinion shifts to 0 or 1).

## Setup Instructions

### Prerequisites

Ensure Python 3.x is installed on your system. The required Python packages are listed in `requirements.txt`.

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/AnnaTz/opinion-dynamics-simulation.git
   ```
2. Navigate to the cloned directory and install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

### Running the Notebook

Launch Jupyter Notebook or JupyterLab and open `opinion_dynamics.ipynb`. Execute the cells sequentially to explore the simulation setup, run scenarios, and analyze outcomes.
