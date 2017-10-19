# LEAR: Lexical Entailment Attract-Repel
Specialising Word Vectors for Lexical Entailment (Vulić and Mrkšić, 2017).

Contact: Nikola Mrkšić (nikola.mrksic@gmail.com)

This repository contains the code and data for the Lexical Entailment Attract-Repel (LEAR) method presented in [Specialising Word Vectors for Lexical Entailment](https://arxiv.org/abs/1710.06371). The word vectors which achieve the state of the art on the HyperLex dataset can be downloaded [here](LINK-to-GOOGLE-Drive).


### Configuring the Tool

The LEAR tool reads all the experiment config parameters from the ```experiment_parameters.cfg``` file in the root directory. An alternative config file can be provided as the first (and only) argument to ```code/lear.py```. 

The config file specifies:
* the location of the initial word vectors (```distributional_vectors```);
* the sets of linguistic constraints to be injected into the vector space (```antonyms```, ```synonyms_sym```, ```synonyms_asym``` );

The config file also specifies the hyperparameters of the LEAR procedure (set to their default values in ```config/experiment_parameters.cfg```). 

The evaluation directory contains the SimLex-999 dataset (Hill et al., 2014), the SimVerb dataset (Gerz et al., 2016), and the HyperLex dataset (Vulić et al., 2017). 


### Running Experiments

```python code/lear.py config/experiment_parameters.cfg```

Running the experiment loads the word vectors specified in the config file and fits them to the provided linguistic constraints. The procedure prints the updated word vectors to the results directory as ```results/final_vectors.txt``` (one word vector per line). 


### References

The paper which introduces the LEAR procedure:
```
 @Article{Vulic:2017,
  author    = {Ivan Vuli\'{c} and Nikola Mrk\v{s}i\'c},
  title     = {Specialising Word Vectors for Lexical Entailment},
  journal   = {CoRR},
  year      = 2017,
  volume = {abs/1710.06371}
 }
```

If you are using WordNet (Miller, 1995) constraints, please cite these papers. If you are using BabelNet constraints, please cite (Navigli and Ponzetto, 2012).
