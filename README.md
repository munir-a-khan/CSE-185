# CSE 185 · Introduction to Computer Vision

MATLAB coursework from **UC Merced · Spring 2024**, covering image warping, spatial and frequency filtering, image pyramids, template matching, edges, and face-image comparison.

The original lab folders include source code, input images, saved results, and ZIP snapshots. Start with the expanded source folders below; no extraction is needed to browse them.

## Lab guide

| Lab | Scope | Start here |
| --- | --- | --- |
| [Lab 1](Lab_1/) | Six numbered image assets; no MATLAB source is included | [Image collection](Lab_1/) |
| [Lab 2](Lab_2/) | Forward/backward rotation and median filtering | [Lab02.m](Lab_2/Lab02.m), [median_filter.m](Lab_2/median_filter.m) |
| [Lab 3](Lab_3/lab3/) | Sobel responses and Gaussian filtering | [lab03.m](Lab_3/lab3/lab03.m), [filter implementations](Lab_3/lab3/) |
| [Lab 4](Lab_4/) | FFT frequency separation and hybrid images | [separate_frequency.m](Lab_4/separate_frequency.m), [lab04.m](Lab_4/untitled/lab04.m), [hybrid_image.m](Lab_4/untitled/hybrid_image.m) |
| [Lab 5](Lab_5/) | Gaussian/Laplacian pyramids and SSD/normalized-correlation template matching | [Source](Lab_5/Code/), [saved results](Lab_5/imgs/) |
| [Lab 6](Lab_6/) | Sobel magnitude/orientation, edge thresholding, Canny edges, and multiscale features for face-image comparison | [lab06_edge.m](Lab_6/lab06_edge.m), [lab06_face.m](Lab_6/lab06_face.m), [multiscale_sobel_feature.m](Lab_6/multiscale_sobel_feature.m) |

## Working with the code

Use **MATLAB with Image Processing Toolbox**: the labs call functions such as `im2col`, `col2im`, `fspecial`, `imresize`, and `edge`. No MATLAB release or dependency lockfile is recorded. Octave compatibility has not been verified.

Scripts read image filenames relative to MATLAB's current folder and write results there, potentially replacing saved JPEGs. Work in a disposable copy if you want to preserve the original results. Keep each lab's helpers on the path separately: Labs 3 and 5 both define `gaussian_filter`, and Labs 3 and 6 both define `sobel_filter`.

From the repository root in MATLAB, these entry points have their named inputs and helpers in the same folder:

```matlab
cd('Lab_2')
Lab02
```

Or, in a fresh session starting at the repository root:

```matlab
cd('Lab_3/lab3')
lab03
```

These commands are checked against the source and file layout; they have **not been executed in MATLAB**. Lab 2 writes `rotate_1.jpg`, while the committed backward-rotation result is named `rotate_1 2.jpg`.

### Inputs and limitations in later labs

- **Lab 4:** `lab04.m` expects `lena.jpg`, `marilyn.jpg`, and `einstein.jpg` in its working folder. They are absent from `Lab_4/untitled/` and its ZIP snapshot. A `lena.jpg` is available in [Lab 3](Lab_3/lab3/lena.jpg). The script also needs the parent folder on the MATLAB path to find `separate_frequency.m`.
- **Lab 5:** `lab05_task1.m` expects `lena.jpg`; `lab05_task2.m` expects `einstein1.jpg`, `einstein2.jpg`, and `template.jpg`. These inputs are absent from `Lab_5/Code/`. Saved outputs are in `Lab_5/imgs/`, whereas the scripts write to the current folder. The Lab 5 Gaussian helper reshapes its kernel inside the pixel loop; its behavior needs review before treating the pyramid script as a validated implementation.
- **Lab 6:** `lab06_edge.m` expects `lena.jpg`, which is absent from `Lab_6/`. `lab06_face.m` expects an untracked `att_face.mat` dataset containing `id_training`, `id_testing`, `face_training`, and `face_testing`. Its predictions use the nearest training-array index directly, so the reported accuracy also depends on how dataset IDs are organized. Accuracy values in source comments are historical notes, not independently reproduced results.

## Saved result

The repository includes this original Lab 6 gradient-orientation visualization; it is shown as a saved artifact, not a newly generated result.

![Saved Sobel gradient-orientation visualization from Lab 6](Lab_6/lena_sobel_orientation.jpg)

[Browse all Lab 6 images and source](Lab_6/).
