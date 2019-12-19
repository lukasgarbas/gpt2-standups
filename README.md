# Experimenting with finetuning GPT-2

Training gpt-2 with different standup comedy transcripts to see if it can come up with something funny.

_run_generation.py_ and _run_lm_finetuning.py_ taken from [huggingface transformers](https://github.com/huggingface/transformers/tree/master/examples) 🦄 

###### Examples coming...

I'm using google colab to finetune and generate texts

##### Finetune: 
```bash
!python run_lm_finetuning.py \
  --output_dir="/gpt2-standups/models/john" \
  --model_type="gpt2" \
  --model_name_or_path=gpt2 \
  --do_train \
  --train_data_file="standups/john.txt" \
  --num_train_epochs=6 \
  --overwrite_output_dir \
  --per_gpu_train_batch_size 1 \
  --save_steps 10000\
```

##### Generate text: 
```bash
!python run_generation.py \
  --model_type="gpt2" \
  --model_name_or_path="/gpt2-standups/models/john" \
  --length=100
```