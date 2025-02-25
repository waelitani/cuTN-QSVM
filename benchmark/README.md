## cutn-qsvm benchmark
### 1. Single Data Pair with Single GPU
```
mpirun -np 1 python banchmark_qsvm_tnsm-mpi_sgpu.py
```
#### - Runtime compare with v100, a100 and h100 GPU 
![alt text](figure/figure_sgpu.png)

#### - Runtime detail with h100 GPU
![alt text](figure/figure1_sgpu.png)

### 2. Multiple Data Pairs with Multiple GPUs
```
#!/bin/bash
#SBATCH -J mgpu -p nchc
#SBATCH --nodes=1 --ntasks-per-node=8 --cpus-per-task=10
#SBATCH --gres=gpu:8
#SBATCH --mem-bind=no

ml purge
ml cuq/12
source /beegfs/_venv/cuq24cu12/bin/activate
mpirun python banchmark_qsvm_tnsm-mpi_mgpu.py
```
#### - mgpu with v100
![alt text](figure/figure2_mgpu_v100.png)

#### - mgpu with h100
![alt text](figure/figure3_mgpu_h100.png)