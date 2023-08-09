#SPDX AI Team Minutes,  August 2, 2023

## Attendees
* Jay White (Microsoft)
* Karen Bennet (IEEE)
* Iam Palatnik
* Gopi  (Huawei)
* Kate Stewart (LF)

## Minutes
### News
* Atom - from VEX summit worth looking at further.  - https://wandb.ai/site
* Weights and biases services - tracking variables of training.    Internal company data. 
* Group in Europe, calling "standard", but it's an SBOM.   Worth approaching.  AI: Karen to provide link, and Kate to see if LF has contacts to those folk. 

### Relationship types 
* Why Licensing Relationships?
   *  Noting that it might change over time.
* Gopi - Add validated on & interpreted on relationships.   Models and Datasets.
   * During training of a machine learning model.    learning,  validation & testing data.   Once hyper parameters are tuned they use testing data.   So this is for the model being trained with the datasets.   Future proof by adding the validation there. 
   * In models,  use X for dataset,  then went back to retrain with other data.    As long as its listed by "trained on", should be fine, even if you throw it away. 
   * Tools using automating all the steps.   How long does the model sit with the original trained dataset? 
   * Applied and learned knowledge.   Next bit of teaching will be compounded on top.  Conflicting could be problem with training model.   Is there a way to scrub out the original impact.   MIB - member rewipe. 
   * Active area of research - model forgetting specific things?   More that we use, controlled deviousness/pen testing, how can it be remediated.   Introduction of new malicious informaiton is "live", and "applied".   Results in model confusion,  logic may be surfaced, but not always.   
   * Models can be fine tuned any number of times... how should we handle.
      * Model A has been trained, and it is should called Model B.   One SBOM for each time you train.
      * Huggingface,  for LoRA - finish fine tuning, has additional file with weights,  model is different.   
      * Parameterization in use problem,  isn't being handled right now.  
      * Challenge is how to document when trained, scrap dataset using,  build profile may have insights.
      * During development progress; in some cases may want to track in detail. 
      * Question is :  Append vs Replace.   
      * Learnings in organization - want some way to mark.   Consider usage profile fields?
    * Choice of how going to "serve" model,  via container for instance.   License changing for instance
    * Stable diffusion type models:   is a pathological case for instance: https://huggingface.co/CalderaAI/30B-Lazarus,  this type of thing is also gonna be very prevalent with stable diffusion type models.   Lol,  diffusion type models are growing in popularity especially since the launch of Lamba-2
    * As long as model size is reasonable, can ship with code;  however some of the bigger are relying the larger services, and lot of hardware to train the model. 
    * Adaptors - Adapted with LoRa with a spanish hat.  So it speaks spanish.  
        * https://adapterhub.ml/ this is a repository of adapters for instance
    * Presence Type --> pulled into Core
    
* Karen to share a full set of open models she's spotted in readings.  
* Seeing by diagram, why matters.    Errors coming in, in different ways - bad actors, poisoned data, ...
* Deep Learning course on debugging models.   
    
* Desired Diagrams for use cases:
   * Show the original being built.
   * Original model trained by a set of datasets --> "Trained model" 
   * Adding additional training data that updates the model --> "Fine tuned model"
   * Sharing a trained model in a container
   * Sharing model in container exposed through a web service  (how most models are deployed these days)
   * Show trained model being discarded, and replaced with a newly trained version of the model (hazard/vulnerabiity scenario).
   * Show how go about debugging a model with a dataset.
   * Show how model is generated from a set of models "frankenstein"
   * Show model being used with "adaptors" (aka hats)  - adaptors used.  
