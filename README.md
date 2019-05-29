This is a work-in-progress [website](https://fanwangecon.github.io/CodeDynaAsset/) of collections of code for solving several infinite horizon exogenous incomplete dynamic asset models, produced by [Fan](https://fanwangecon.github.io/). Materials gathered from various [projects](https://fanwangecon.github.io/research).

Generally, looped, vectorized, efficient-vectorized versions of the same code are shown. Looped codes are shown for clarity, vectorized codes are shown for speed. Main functions rely on support functions which are all included in the repository and some key files are shown below.

To test functions, clone the project via github. See [here](docs/gitsetup.md) for Github set up. Each function is written with default parameters and is directly callable. Run on computers with at least 16GB of memory. Files tested with [Matlab 2019a](https://www.mathworks.com/company/newsroom/mathworks-announces-release-2019a-of-matlab-and-simulink.html). Solution algorithms are language agnostic, codes shown in Matlab for ease of replicability. Speed difference across languages is not significant when solving models using vectorized grid-based solution algorithms.

Please contact [FanWangEcon](https://fanwangecon.github.io/) for issues or problems.


<!-- Each self-contained folder includes all codes required to invoke each model.

Each model folder has this file structure:

1. invoke: file that invoke, call the file in the solve folder, to loop over various parameter combinations
2. solve: the solution code for solving the model, including solution code for optimization and code for finding distributions. Generally, several versions of codes are included for solving the model using different algorithms.
3. tools: files, functions, specific to this model that helps solving things
4. params: including files that contain different parameter combinations

There is a an overall tools folder that contains codes/files that are shared across folders.

Within each subfolder, there is possibly a *_profile* folder for html files that are profiling results (only several main files are stored, so most links are not clickable), and a html file with files generated by matlab publish. -->

# Solving the One Asset One Shock Problem
<!-- https://fanwangecon.github.io/CodeDynaAsset/m_az -->

The standard heterogeneous agent model with assets and shocks. Endogenous asset. Income is a function of exogenous wage and endogenous interest earnings. Exogenous incomplete borrowing and savings. Wage shocks follow AR1.

## Optimization

Solving for the policy functions.

1. Solution Main:
    - Looped Solution: \| [**m**](https://github.com/FanWangEcon/CodeDynaAsset/blob/master/m_az/solve/ff_az_vf.m) \| [**html**](https://fanwangecon.github.io/CodeDynaAsset/m_az/solve/html/ff_az_vf.html) \| [**profile**](https://fanwangecon.github.io/CodeDynaAsset/m_az/solve/profile/default_p3/file3.html) \|    
2. Policy and Value Function Analysis:
    - post processing: \| [**m**](https://github.com/FanWangEcon/CodeDynaAsset/blob/master/m_az/solvepost/ff_az_vf_post.m) \| [**html**](https://fanwangecon.github.io/CodeDynaAsset/m_az/solvepost/html/ff_az_vf_post.html) \|
    - post graphing: \| [**m**](https://github.com/FanWangEcon/CodeDynaAsset/blob/master/m_az/solvepost/ff_az_vf_post_graph.m) \| [**html**](https://fanwangecon.github.io/CodeDynaAsset/m_az/solvepost/html/ff_az_vf_post_graph.html) \|
3. Support:
    - set default parameters: \| [**m**](https://github.com/FanWangEcon/CodeDynaAsset/blob/master/m_az/paramfunc/ffs_az_set_default_param.m) \| [**html**](https://fanwangecon.github.io/CodeDynaAsset/m_az/paramfunc/html/ffs_az_set_default_param.html) \|
    - set functions: \| [**m**](https://github.com/FanWangEcon/CodeDynaAsset/blob/master/m_az/paramfunc/ffs_az_set_functions.m) \| [**html**](https://fanwangecon.github.io/CodeDynaAsset/m_az/paramfunc/html/ffs_az_set_functions.html) \|
    - generate states, choices, and shocks grids: \| [**m**](https://github.com/FanWangEcon/CodeDynaAsset/blob/master/m_az/paramfunc/ffs_az_get_funcgrid.m) \| [**html**](https://fanwangecon.github.io/CodeDynaAsset/m_az/paramfunc/html/ffs_az_get_funcgrid.html) \|


## Endogenous Distributions

Solving for the asset distribution
