# Model design:

## Model Description
The model was a simple model built with a single embedding BERT layer and two Dense layers. The model may have performed far better with an additional Dropout / Conv1D layer. Will attemp the same in the next few experiments

Model: "model_1"
__________________________________________________________________________________________________
Layer (type)                    Output Shape         Param #     Connected to                     
==================================================================================================
ids (InputLayer)                [(None, 512)]        0                                            
__________________________________________________________________________________________________
masks (InputLayer)              [(None, 512)]        0                                            
__________________________________________________________________________________________________
bert (TFBertMainLayer)          TFBaseModelOutputWit 108310272   ids[0][0]                        
                                                                 masks[0][0]                      
__________________________________________________________________________________________________
dense_2 (Dense)                 (None, 512)          393728      bert[1][1]                       
__________________________________________________________________________________________________
dense_3 (Dense)                 (None, 64)           32832       dense_2[0][0]                    
__________________________________________________________________________________________________
outputs (Dense)                 (None, 5)            325         dense_3[0][0]                    
==================================================================================================
Total params: 108,737,157
Trainable params: 426,885
Non-trainable params: 108,310,272
__________________________________________________________________________________________________

## Links:
Model built for the batches of 16 samples:
https://drive.google.com/drive/folders/1O4WGG6J26Q-umVjiKlnjKeLUFXKYf1eR?usp=sharing
.h5 file: https://drive.google.com/file/d/1-N4ppa65F68lwiq4YlieWhaUr3Z2Dj1a/view?usp=sharing

Model built for batches of 32 samples:
https://drive.google.com/drive/folders/1nSQ9U0UKXN-v0pilD_2eaH3m15Sjie4t?usp=sharing
.h5 file: https://drive.google.com/file/d/1-Gu1yx84fNveuxFDleCOdVxTElfbKDbP/view?usp=sharing
