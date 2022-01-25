# MARS: Markov Molecular Sampling for Multi-objective Drug Discovery

Thanks for your interest! This is the code repository for our ICLR 2021 paper [MARS: Markov Molecular Sampling for Multi-objective Drug Discovery](https://openreview.net/pdf?id=kHSu4ebxFXY). 

## Dependencies

The `conda` environment is exported as `environment.yml`. You can also manually install these packages:

```bash
conda install -c conda-forge rdkit
conda install tqdm tensorboard scikit-learn
conda install pytorch cudatoolkit=11.1 -c pytorch -c conda-forge
conda install -c dglteam dgl-cuda11.1

# for cpu only
conda install pytorch cpuonly -c pytorch
conda install -c dglteam dgl
```

## Run

> Note: Run the commands **outside** the `MARS` directory.

To extract molecular fragments from a database:

```bash
python -m MARS.datasets.prepro_vocab
```

To sample molecules:

```bash
python -m MARS.main --train --run_dir runs/RUN_DIR
```

## Evaluation and Generated Molecules

The generated molecules are evaluated at each step and the results are stored in `runs/RUN_DIR` (`runs/debug` by default). Please refer to tensorboard files for the evaluation results and `mols.txt` for all the molecules generated during sampling. 

The experiment results we listed in the paper are obtained by averaging the outcomes of 10 independent sampling paths. For each sampling path, we record the evaluation results of the step that produces the highest PM score. 

## Citation

```
@inproceedings{
    xie2021mars,
    title={{\{}MARS{\}}: Markov Molecular Sampling for Multi-objective Drug Discovery},
    author={Yutong Xie and Chence Shi and Hao Zhou and Yuwei Yang and Weinan Zhang and Yong Yu and Lei Li},
    booktitle={International Conference on Learning Representations},
    year={2021},
    url={https://openreview.net/forum?id=kHSu4ebxFXY}
}
```
