# NLP and Generative AI on OKCupid Dataset

The dataset can be found here:
https://www.kaggle.com/datasets/andrewmvd/okcupid-profiles

This project uses Hugging Face and unitary.ai NLP models to perform the following:

1.) Screen people out who have harmful profiles and pair users together by vectorizing their biographies (creating from concatenating all essays the user filled out) and computing the cosine similarity between all users who match each other's demographic preferences. Furthermore, show the user their highest compatible matches from the existing users with a passed-in biography only if their biography is not deemed harmful.
- Models used: all-MiniLM-L6-v2 (sentence-bert), Detoxify
- File: sentencebert_classify_matcher.ipynb

2.) Fine-tune a GPT-2 model on computed matches that exceed a cosine similarity threshold by processing them into one text file.
- Models used: GPT-2
- File: finetuning_gpt2.ipynb

3.) Generate profiles using fine-tuned GPT-2 model, ensuring that both the user is not passing in a harmful profile and the user is not shown a harmful profile.
- Models used: Fine-tuned GPT-2, Detoxify
- File: finetuned_gen.ipynb
