# Cellular Division in ANML - IFT 6760B Project
Adapting ANML to test it's performance on more plausible continual learning settings

This projet is based on papers:
*ANML: Learning to Continually Learn (ECAI 2020)* 
[arXiv Link]<https://arxiv.org/abs/2002.09571>




## How to Run 

Meta-train your network(s). To modify the network architecture, see modelfactory.py in the model folder. Depending on the architecture you choose, you may have to change how the data is loaded and/or preprocessed. See omniglot.py and task_sampler.py in the datasets folder.

```
python mrcl_classification.py --rln 7 --meta_lr 0.001 --update_lr 0.1 --name mrcl_omniglot --steps 20000 --seed 9 --model_name "Neuromodulation_Model.net"
```

Evaluate your trained model. RLN tag specifies which layers you want to fix during the meta-test training phase. For example, to have no layers fixed, run:

```
python evaluate_classification.py --rln 0  --model Neuromodulation_Model.net --name Omni_test_traj --runs 10

```

### Prerequisites

Python 3
PyTorch 1.4.0
Tensorboard

##  Built from :
* [ANML](https://github.com/uvm-neurobotics-lab/ANML)
* [OML/MRCL](https://github.com/khurramjaved96/mrcl)

