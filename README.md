# Together Port of Faster Transformer for Bloomchat Model


### build the docker container

    docker build -t together_ft_bloom --file Bloom-Together-Dockerfile .


### run convert file (inside the built container)


    nvidia-docker run  --ipc=host --network=host --name test_together_ft_bloom -ti -v /PATH_TO_MODEL_STORAGE:/workspace/FasterTransformer/build/model together_ft_bloom bash

    python /workspace/FasterTransformer/examples/pytorch/gpt/utils/huggingface_bloom_convert.py -i /workspace/FasterTransformer/build/model/bloom-ock-dolly-oasst1 -o /workspace/FasterTransformer/build/model/ft-bloom-ock-dolly-oasst1-tp8 -tp 8 -dt fp16 -v

