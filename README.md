# bert-squad-demo
Demo web server app that shows how BERT model trained on SQuAD dataset deals with the machine
comprehension task.

It was implemented for the purposes of presentation on STX Next Tech Power Summit 2019.
Slides from the presentation are available [here](slides/whats_new_in_word_vectors.pdf).

## Quick guide

Before running the app, please make sure that you have all [requirements](requirements.txt) installed 
and [download](model/README.md) BERT model for machine comprehension.

To run the server, navigate into the main project's directory and type

```
$ flask run
```

Requests sent to the BERT web server should have the following form:

```json
{
  "context": "Bert is a yellow Muppet character...",
  "question": "Who was the first Bert performer?"
}  
```

You can expect answers of the form:

```json
{
    "answer": "Frank Oz"
}
```

# train command
python run_squad.py   --bert_model bert-base-uncased   --do_train   --do_predict   --do_lower_case   --train_file $SQUAD_DIR/train-v1.1.json   --predict_file $SQUAD_DIR/dev-v1.1.json   --train_batch_size 8   --learning_rate 3e-5   --num_train_epochs 2.0   --max_seq_length 384   --doc_stride 128   --output_dir /demo-mount/bert-squad-demo/model