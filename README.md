zip -r foo.zip foodir 

# https://replicate.com/stability-ai/sdxl#training-inputs


> export REPLICATE_API_TOKEN=r8_...
> python

import replicate

training = replicate.trainings.create(
    version="stability-ai/sdxl:d830ba5dabf8090ec0db6c10fc862c6eb1c929e1a194a5411852d25fd954ac82",
    input={
        "input_images": "https://github.com/iamsml/training-data/raw/main/chair.zip",
        "token_string": "@chair",
        "mask_target_prompts": "photo of a chair",
    },
    destination="iamsml/article-chair-sdxl"
)
print(training)