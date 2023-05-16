# wand_dhseg_playground
a playground for making a llm with langchain that will either write the integration itself or acuratly id and req methods to integrate any repo, in this case dhSegment, with wandb for training and logging.

### Main repos / readthedocs:

DHSegment: https://github.com/dhlab-epfl/dhSegment, https://github.com/dhlab-epfl/dhSegment-torch

DHSegment Docs: https://dhsegment.readthedocs.io/en/latest/

Wandb Docs: https://docs.wandb.ai/

### Main pipeline:

- dataloader:
    Utilizes [llama index](https://github.com/jerryjliu/llama_index/tree/main/llama_index/readers/github_readers) dataloaders to format text from assests such as a locally downloaded git_repo and the base_url of a readthedocs page to extract and format all the text / code from these resources in a format legible to langchain tools for fine-tuning a LLM.
    
- embeddings and ML databanks:
    Utilizes [FAISS](https://github.com/facebookresearch/faiss) and [Deep Lake](https://docs.activeloop.ai/) to store and access embedded tensors which are fed to a LLM as an index, or extended / highligted reference bank so that the LLM can refer to assest that it may have been previously unexposed or underexposed to.
    
- combined docs:
    By combining the docs from [wandb](https://docs.wandb.ai/) and the user inputed repo's and documentation this customized llm can offer specific use-cases and examples of ways to train, visualize, and preform inference on any ML model documented on git or with readthedocs. Assisting with logging, and tracking of ML projects to wandb dashboards as well as making docs more legible and callable. 



