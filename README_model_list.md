
In Jupyter 
#### Training
```python
from mlmodels.models import module_load, data_loader, create_model, fit, predict, stats
from mlmodels.models import load #Load model weights


model_uri    = "model_tf.1_lstm.py"
model_pars   =  {  "num_layers": 1,
                  "size": ncol_input, "size_layer": 128, "output_size": ncol_output, "timestep": 4,
                }
data_pars    =  {"data_path": "/folder/myfile.csv"  , "data_type": "pandas" }
compute_pars =  { "learning_rate": 0.001, }
out_pars     =  { "path": "ztest_1lstm/", "model_path" : "ztest_1lstm/model/"}


module        =  module_load( model_uri= model_uri )  #Load file definition
model         =  model_create(module, model_pars)    # Create Model instance
model, sess   =  fit(model, module, data_pars)       # fit the model

metrics_val   =  metrics( model, sess, ["loss"])     # get stats
model.save( out_pars['path'], model, module, sess,)

```

#### Inferencmodel/e
```python
model = load(folder)    #Create Model instance
ypred = module.predict(model, module, data_pars, compute_pars)     # predict pipeline
```


#### 
``` CLI examples

ml_models --do                    
    "testall"     :  test all modules inside model_tf
    "test"        :  test a certain module inside model_tf


    "model_list"  :  #list all models in the repo          
    "fit"         :  wrap fit generic m    ethod
    "predict"     :  predict  using a pre-trained model and some data
    "generate_config"  :  generate config file from code source


ml_optim --do
  "test"      :  Test the hyperparameter optimization for a specific model
  "test_all"  :  TODO, Test all
  "search"    :  search for the best hyperparameters of a specific model



### Command line tool sample

#### generate config file
    ml_models  --do generate_config  --model_uri model_tf.1_lstm.py  --save_folder "c:\myconfig"

#### TensorFlow LSTM model
    ml_models  --model_uri model_tf/1_lstm.py  --do test

#### PyTorch models
    ml_models  --model_uri model_tch/mlp.py  --do test
    
    
#### Custom  Models
    ml_models --do test  --model_uri "D:\_devs\Python01\gitdev\mlmodels\mlmodels\model_tf_lstm.py"




#### Distributed Pytorch on CPU (using Horovod and MPI on Linux, 4 processes)  in model_tch/mlp.py
    mlmodels/distri_torch_mpirun.sh   4    model_tch.mlp    mymodel.json



#### Model param search test
    ml_optim --do test


#### For normal optimization search method
    ml_optim --do search --ntrials 1  --config_file optim_config.json --optim_method normal
    ml_optim --do search --ntrials 1  --config_file optim_config.json --optim_method prune  ###### for pruning method


#### HyperParam standalone run
    ml_optim --modelname model_tf.1_lstm.py  --do test
    ml_optim --modelname model_tf.1_lstm.py  --do search
```



```


```



```
Model list 



mlmodels.model_dev.ml_mosaic.py
mlmodels.model_dev.mytest.py


mlmodels.model_flow.mlflow_run.py


mlmodels.model_gluon.gluon_automl.py
mlmodels.model_gluon.gluon_deepar.py
mlmodels.model_gluon.gluon_ffn.py
mlmodels.model_gluon.gluon_prophet.py


mlmodels.model_keras.00_template_keras.py
mlmodels.model_keras.01_deepctr.py
mlmodels.model_keras.02_cnn.py


mlmodels.model_rank.LambdaRank.py
mlmodels.model_rank.load_mslr.py
mlmodels.model_rank.metrics.py
mlmodels.model_rank.RankNet.py


mlmodels.model_sklearn.model.py


mlmodels.model_tch.cnn_classifier.py
mlmodels.model_tch.data_prep.py
mlmodels.model_tch.mlp.py
mlmodels.model_tch.nbeats.py
mlmodels.model_tch.pplm.py
mlmodels.model_tch.sentence_transformer.py
mlmodels.model_tch.transformer_classifier.py


mlmodels.model_tf.10_encoder_vanilla.py
mlmodels.model_tf.11_bidirectional_vanilla.py
mlmodels.model_tf.12_vanilla_2path.py
mlmodels.model_tf.13_lstm_seq2seq.py
mlmodels.model_tf.14_lstm_attention.py
mlmodels.model_tf.15_lstm_seq2seq_attention.py
mlmodels.model_tf.16_lstm_seq2seq_bidirectional.py
mlmodels.model_tf.17_lstm_seq2seq_bidirectional_attention.py
mlmodels.model_tf.18_lstm_attention_scaleddot.py
mlmodels.model_tf.19_lstm_dilated.py
mlmodels.model_tf.1_lstm.py
mlmodels.model_tf.20_only_attention.py
mlmodels.model_tf.21_multihead_attention.py
mlmodels.model_tf.22_lstm_bahdanau.py
mlmodels.model_tf.23_lstm_luong.py
mlmodels.model_tf.24_lstm_luong_bahdanau.py
mlmodels.model_tf.25_dnc.py
mlmodels.model_tf.26_lstm_residual.py
mlmodels.model_tf.27_byte_net.py
mlmodels.model_tf.28_attention_is_all_you_need.py
mlmodels.model_tf.29_fairseq.py
mlmodels.model_tf.2_encoder_lstm.py
mlmodels.model_tf.3_bidirectional_lstm.py
mlmodels.model_tf.4_lstm_2path.py
mlmodels.model_tf.50lstm attention.py
mlmodels.model_tf.5_gru.py
mlmodels.model_tf.6_encoder_gru.py
mlmodels.model_tf.7_bidirectional_gru.py
mlmodels.model_tf.8_gru_2path.py
mlmodels.model_tf.9_vanilla.py
mlmodels.model_tf.access.py
mlmodels.model_tf.addressing.py
mlmodels.model_tf.autoencoder.py
mlmodels.model_tf.dnc.py



```

