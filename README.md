# Connected Component Labeling

This repo is based on the pseudo code of [The Improved Run-based Connected-component Labeling (IRCL) algorithm](https://www.semanticscholar.org/paper/A-Run-Based-One-and-a-Half-Scan-Connected-Component-He-Chao/6003714755aef12472dd0d52760f6486a34dbe64) proposed by He et al.

---

## Keywords

- As in most labeling algorithms, the authors assume that all pixels on the edges of an image are background pixels, and only consider **eight-connectivity**.
- **Run**: A run is a block of contiguous object pixels in a row. In some previous two scan algorithms, the run data, which are obtained during the first scan, are recorded in a queue and used for detecting the connectivity of runs in the later processing. IRCL algorithm uses run data for labeling directly. The relabeling step is not necessary.
- **Label equivalence**
- **Run-length encoding**
- **Raster scan**

## Algorithm phases

- **First pass**: Traverse the pixel one by one in the order of raster scanning direction. If the pixel is the object pixel, do the labeling task and resolve equivalence. After this step, the equivalent label sets are updated.
- **Second pass**: Update the object pixel belonging to each run by the run's representative label. This algorithm just scans through the run data so the background pixels are only scanned once.

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
