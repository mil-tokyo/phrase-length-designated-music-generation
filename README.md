# REMI + Ph&BC

## Installation
Clone the original REMI code (Pop Music Transformer):
```sh
git clone https://github.com/YatingMusic/remi.git
cd remi
git checkout 6d40725
```

Clone the diff file in this repository:
```sh
git clone https://github.com/mil-tokyo/phrase-length-designated-music-generation.git -b master --single-branch
```

Apply the diff file to the REMI code:
```sh
patch -p1 < phrase-length-designated-music-generation/diff.patch
```

Clone the POP909 dataset and its annotations:
```sh
git clone https://github.com/music-x-lab/POP909-Dataset.git
git clone https://github.com/Dsqvival/hierarchical-structure-analysis.git
```

Please refer to [the original REMI repository](https://github.com/YatingMusic/remi) for instructions on how to install dependencies.

## Training
NOTE: This is training from scratch (sorry for confusing you).
```sh
python finetune.py
```
After training, please choose which checkpoint you want to try and change the checkpoint names you choose into "model".
- "model-xxx-y.zzz.data-00000-of-00001" → "model.data-00000-of-00001"
- "model-xxx-y.zzz.index" → "model.index"
- "model-xxx-y.zzz.meta" → "model.meta"

## Inference
After changing the phrase configuration in the main.py, run it.
```sh
python main.py
```
"from_scratch.midi" will be generated in the "result" folder.


## Reference
- REMI code (Pop Music Transformer)  
https://github.com/YatingMusic/remi
- POP909 dataset  
https://github.com/music-x-lab/POP909-Dataset
- POP909 annotation (Automatic Analysis and Influence of Hierarchical Structure on Melody, Rhythm and Harmony in Popular Music)
https://github.com/Dsqvival/hierarchical-structure-analysis
