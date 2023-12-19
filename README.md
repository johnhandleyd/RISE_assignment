# RISE - NLP Researcher Assignment by John Handley

## Instructions to run the code

### Paths
In the Jupyter notebook you can find all the code to run this file; it would only be necessary to change some of paths of the following variables or functions:
- *args* for the Trainer (if to fine-tune the model again)
- trainer.save_model(*path*) (to save the model locally if desired)
- plot_loss(*path*) (to plot the loss with the *trainer_state.json* files)

### Included files
These are the files included:
- IPYNB Jupyter Notebook
    - *RISE.ipynb*
- *trainer_state* files with metrics information for Systems A & B; for plotting the loss for validation and test sets
    - *bert-finetuned-ner-A_[val\_]trainer_state.json*
    - *bert-finetuned-ner-B_[val\_]trainer_state.json*
- Information files
    - *README.md*
    - *requirements.txt*

## Results
This assignment includes the preprocessing of the MultiNERD dataset into two systems, tokenization, fine-tuning to the BERT base cased model and testing on a few phrases of both systems.

### Findings
Looking at the metrics, both systems A & B performed highly, with accuracies of 98% and 99% respectfully, and similar results for precision, recall and F1. 

On the phrases used to test the performance of both models, system A spotted most entities with a high score, and system B spotted all entities with high scores.

Though, system A showed some mistakes when tested on the custom phrases, like mistagging "Minyans" (which was separated into subwords) and the word "bacterial" as DIS. It also missed some entities ("fish" as FOOD, "meningitis" as DIS).

### Limitations

Though the systems performed well, I believe  it would be appropriate to try and address the mistakes system A made as well as try to assess if system B has any weaknesses that could be addressed as well.

Finally, it would have been ideal to compute a confusion matrix to display the false predictions of the model per entity, to spot the weaknesses and strengths and tune the fine-tuning or dataset in order to address the weaknesses. In a real-case scenario, I would have continued down that path, with more time and resources.
