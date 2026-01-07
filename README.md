# FaRatriver


## scripts

### SFT (Supervised Fine-Tuning)


```bash
export PIP_INDEX_URL="https://pkg.geely.com/artifactory/api/pypi/pypi/simple"
export PIP_EXTRA_INDEX_URL="https://pkg.geely.com/artifactory/api/pypi/nvidia-pypi-remote-hz/simple"
export NCCL_DEBUG=VERSION
pip install vllm==0.5.0
export LD_LIBRARY_PATH=/usr/local/lib/python3.10/dist-packages/nvidia/cuda_runtime/lib/:$LD_LIBRARY_PATH
export MLP_WORKER_NUM=1
cd {PROJECT_PATH}

BASE_MODEL={YOUR_BASE_MODEL} \
DATA_PATH={YOUR_DATA_PATH} \
OUTPUT_PATH={YOUR_OUTPUT_PATH} \
BATCH_SIZE=2 \
LR=1e-4 \
EPOCH=5 \
EMBEDDING_LOSS_WEIGHT=0.3 \
LOGITS_LOSS_WEIGHT=0.4 \
ANSWER_TOKEN_LOSS_WEIGHT=0.4 \
OUTPUT_DIR={YOUR_DIR} \
source {PROJECT_PATH}/run_distill_template.sh

```
