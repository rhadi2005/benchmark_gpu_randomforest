# tensorflow_ds
R&amp;D for implementing tensorflow in Saturn Cloud

Dataset: `clothing-dataset-small` is on S3 but loading from disk is necessary for training at this time.

## Current Scripts

* Inference parallel on cluster: `inference.ipynb`
* Training single node (slowish): `training_singlenode.ipynb`
* Training multi-gpu single machine (fast): `training_multigpu.ipynb` 
* Training multi-gpu multi-machine (not yet working): `training_cluster.ipynb`


## Things to Watch For

* Tensorflow GPU training runs (at least) do not release memory upon concluding. These will use all or nearly all GPU memory available.
* I've used Weights and Biases throughout this code to monitor GPU performance - if running this, user should set their own Saturn env credential for wandb.
