# NVIDIA AI Workbench: Introduction
This is an [NVIDIA AI Workbench](https://developer.nvidia.com/blog/develop-and-deploy-scalable-generative-ai-models-seamlessly-with-nvidia-ai-workbench/) example Project that demonstrates how to p-tune and prompt tune a NeMo-Megatron LLM using the NeMo Framework. We will first p-tune a GPT model on sentiment analysis and intent and slot classification tasks. Then, we will show how to add the SQuAD question-answering task to the same model we already p-tuned once. Users in the [AI Workbench Beta Program](https://developer.nvidia.com/ai-workbench-beta) can get up and running with this Project in minutes. 

Have questions? Please direct any issues, fixes, suggestions, and discussion on this project to the DevZone Members Only Forum thread [here](https://forums.developer.nvidia.com/t/support-workbench-example-project-nemo-p-tuning/278370/1). 

## Project Description
P-tuning and prompt tuning are both methods that are parameter efficient alternatives to fine-tuning pretrained language models. Our NeMo implementation makes it possible to use one pretrained GPT model on many downstream tasks without needing to tune the model’s full set of parameters. It also allows for adding new tasks to your model without overwriting or disrupting previous tasks for which the model has already been p-tuned/prompt-tuned. Because the original model parameters are frozen and never altered by either method, p-tuning/prompt-tuning also avoid catastrophic forgetting issues often encountered when fine-tuning models.

A single pretrained GPT model can use both p-tuning and prompt-tuning. While you must decide to use either p-tuning or prompt-tuning for each task you want your model to perform, you can p-tune your model on a set of tasks A, then prompt tune your same model on a different set of tasks B, then finally run inference on tasks from both A and B at the same time. During prompt-tuning or p-tuning, tasks tuned at the same time must use the same number of virtual tokens. During inference, tasks using differing amounts of virtual tokens can be run at the same time.

We will be using p-tuning to teach our GPT model how to do Question Answering. The dataset we will use is the SQuAD reading comprehension dataset, consisting of questions posed by crowd workers on a set of Wikipedia articles, where the answer to every question is a segment of text. More information on SQuAD can be found on their website or in their paper by Rajpurkar et. al "Know What You Don’t Know: Unanswerable Questions for SQuAD".

## System Requirements:
* Operating System: Ubuntu 22.04
* CPU requirements: None, tested with Intel&reg; Xeon&reg; Gold 6240R CPU @ 2.40GHz
* GPU requirements: Any NVIDIA training GPU, tested with NVIDIA A100-40GB
* NVIDIA driver requirements: Latest driver version
* Storage requirements: 40GB

# Quickstart
The notebook(s) in this project were adapted from the NVIDIA NeMo Github repository, which can be found [here](https://github.com/NVIDIA/NeMo/tree/main/tutorials/nlp).

If you have NVIDIA AI Workbench already installed, you can use this Project in AI Workbench on your choice of machine by:
1. Forking this Project to your own GitHub namespace and copying the clone link

   ```https://github.com/[your_namespace]/<project_name>.git```
   
2. Opening a shell and activating the Context you want to clone into by

   ```
   $ nvwb list contexts
   
   $ nvwb activate <desired_context>
   ```
   
3. Cloning this Project onto your desired machine by running

   ```
   $ nvwb clone project <your_project_url>
   ```
   
4. Opening the Project by

   ```
   $ nvwb list projects
   
   $ nvwb open <project_name>
   ```
   
5. Starting JupyterLab by

   ```
   $ nvwb start jupyterlab
   ```

6. Navigate to the code directory of the project. Then, open the notebook titled ```Multitask_Prompt_and_PTuning.ipynb``` and get started. Happy coding!

---
**Tip:** Use ```nvwb help``` to see a full list of commands. 

---

## Tested On
This notebook has been tested with an NVIDIA A100-40gb GPU and the following version of NVIDIA AI Workbench: ```nvwb 0.2.66 (internal; linux; amd64; go1.18.10; Tue Sep 12 18:50:21 UTC 2023)```

## License
This NVIDIA AI Workbench example project is under the [Apache 2.0 License](https://github.com/NVIDIA/nemo-ptuning/blob/main/LICENSE.txt)
