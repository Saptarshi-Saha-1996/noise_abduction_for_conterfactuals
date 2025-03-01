### *Structural Causal Model*
<img align="right" src="causal_graph.png" alt="causal_graph" width="200"/>

$X_{4}=2\epsilon_{4}+1$
<br>
$X_{6}=\epsilon_{6}-1$
<br>
$X_{5}=3X_{6}+\epsilon_{5}-1$
<br>
$X_{2}=X_{5}-\epsilon_{2}$
<br>
$X_{3}=-3X_{4}+\epsilon_{3}-3$
<br>
$X_{1}=X_{6}-X_{5}+3\epsilon_{1}$
<br>
$Y=X_{1}+2X_{2}-3X_{3}+\epsilon_{Y}$


---

## Experiments

There is three experiments - *i) different seeds experiment*, *ii)sample_size vs train time* and *iii)specific seed experiment*.

* Models:
    * ConditionalSCM: full model
    * ConditionalSCM_partial: partial model

### specific seed experiment

- `specific_seed_experiment/`:  
    - `assets/`: contains plots of the experiment
    - `logs/`: checkpoints for full model and partial model
- `specific_seed_experiment.ipynb` : experiment notebook (similar to `synthetic_data_experiment.ipynb`)



### different seeds experiment
- `different_seeds_experiment/`: contains plots, logs etc. for ten different seeds; also contains reported training time and errors in counterfactuals
- `different_seeds_experiment.ipynb` : statistical error analysis of counterfactuals and training time analysis 
- `different_seeds_experiment.py ` : train the models , generate counterfactuals and estimate errors for ten different seeds 




### sample_size vs train time
- `sample_size_vs_train_time/` :  contains reported training times of two models, plot for visualiztion of training time difference
- `train_time_experiment.ipynb` : create plots for analysis of the training time difference
- `train_time_experiment.py`: run two models for ten different seeds, seven diffrent sample sizes and four different batch sizes. It outputs training times in `sample_size_vs_train_time/training_time.csv`


---

### Structure
- `analysis.py`: contains utility functions for creating plots for sampling capability, noise inference (abduction) capability, counterfactuals and estimating errors 
- `cf_analysis.py`: function for permorning counterfactual prediction
-  `config.py` : important hyperparams
- `data.py` : create dataset from the data generated by the SCM.
- `full_model.py` : full model
- `partial_model.py` : partial model
- `scm.py` : True SCM
- `train.py`: script for training full model or partial model
- `utils.py` :  mkdir function (will be removed)
 - `synthetic_data_experiment.ipynb` : kind of idea scratchpad ... (good place to start for understanding) 

---
