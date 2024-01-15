## Dataset (CULane)
You can download the dataset from https://xingangpan.github.io/projects/CULane.html.

If you download the dataset from the link, you can find some files and we recommand to make below structure. The folders have already been created. Please place the dataset into the corresponding folders.

    dataset
      |
      |----train_set/               # training root 
      |------|
      |------|----driver_23_30frame/
      |------|----driver_161_90frame/
      |------|----driver_182_30frame/
      |
      |----test_set/               # testing root 
      |------|
      |------|----driver_37_30frame/
      |------|----driver_100_30frame/
      |------|----driver_193_90frame/
      |
      |----list/               # testing root 
      |------|
      |------|----test_split/
      |------|----test.txt
      |------|----train.txt
      |------|----train_gt.txt
      |------|----val.txt
      |------|----val_gt.txt


## Test
You can run "test.py" for testing, and it has some mode like following functions
- mode 0 : Visualize results on test set
- mode 1 : Run the model on the given video. If you want to use this mode, enter your video path at line 74 in "test.py"
- mode 2 : Run the model on the given image. If you want to use this mode, enter your image path at line 99 in "test.py"
- mode 3 : Test the model on whole test set, and save result as json file.

You can change mode at line 22 in "parameters.py".

If you want to use other trained model, just change following 2 lines.
```
# In "parameters.py"
line 13 : model_path = "<your model path>/"
# In "test.py"
line 42 : lane_agent.load_weights(<>, "tensor(<>)")
```


## Train
If you want to train from scratch, make line 13 blank in "parameters.py", and run "train.py"
```
# In "parameters.py"
line 13 : model_path = ""
```
"train.py" will save sample result images(in "test_result/"), trained model(in "savefile/").

If you want to train from a trained model, just change following 2 lines.
```
# In "parameters.py"
line 13 : model_path = "<your model path>/"
# In "train.py"
line 54 : lane_agent.load_weights(<>, "tensor(<>)")
```
