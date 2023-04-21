# Connected Component Labeling

This repo is based on the pseudo code of [The Improved Run-based Connected-component Labeling (IRCL) algorithm](https://www.semanticscholar.org/paper/A-Run-Based-One-and-a-Half-Scan-Connected-Component-He-Chao/6003714755aef12472dd0d52760f6486a34dbe64) proposed by He et al.

---

## Keywords

- As in most labeling algorithms, the authors assume that all pixels on the edges of an image are background pixels, and only consider **eight-connectivity**.
- **Run**: A run is a block of contiguous object pixels in a row. In some previous two scan algorithms, the run data, which are obtained during the first scan, are recorded in a queue and used for detecting the connectivity of runs in the later processing. IRCL algorithm uses run data for labeling directly. The relabeling step is not necessary.
- **Label equivalence**
- **Run-length encoding**
- **Raster scan**

## Run

### Requirements

```text
opencv-python
numpy
imutils
```

```bash
pip install -r requirements.txt
```

### Run IRCL algorithm and save the result

```bash
#!/bin/bash
python run.py --image_path images/ \
              --save_dir results/
```

### Export the visualization step by step of the algorithm

```bash
#!/bin/bash
python run.py --image_path images/granularity.jpg \
              --save_dir results/ \
              --save_vis
```
