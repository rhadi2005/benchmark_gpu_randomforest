# tensorflow_ds
R&amp;D for implementing tensorflow in Saturn Cloud



Datasets: 
* `clothing-dataset-small` is on S3 but loading from disk is necessary for training at this time.
* bird data can be downloaded from kaggle, `kaggle datasets download -d gpiosenka/100-bird-species`

## Current Scripts

* Inference parallel on cluster: `inference.ipynb`
* Training single node (slowish): `training_singlenode.ipynb`
* Training multi-gpu single machine (fast): `training_multigpu.ipynb` - uses bird dataset
* Training multi-gpu multi-machine (not yet working): `training_cluster.ipynb`


## Things to Watch For

* Tensorflow GPU training runs (at least) do not release memory upon concluding. These will use all or nearly all GPU memory available.
* I've used Weights and Biases throughout this code to monitor GPU performance - if running this, user should set their own Saturn env credential for wandb.

## Potentially Useful Reference

* https://www.tensorflow.org/api_docs/python/tf/distribute/Strategy
* https://www.tensorflow.org/guide/distributed_training
* https://www.tensorflow.org/tutorials/distribute/multi_worker_with_keras
* https://www.tensorflow.org/api_docs/python/tf/distribute/MultiWorkerMirroredStrategy
* https://keras.io/guides/distributed_training/#multiworker-distributed-synchronous-training
* https://docs.w3cub.com/tensorflow~2.3/distribute/mirroredstrategy.html
* https://github.com/sayakpaul/tf.keras-Distributed-Training/blob/master/Multi_GPU_Training-WB.ipynb
* https://towardsdatascience.com/distributed-training-in-tf-keras-with-w-b-ccf021f9322e