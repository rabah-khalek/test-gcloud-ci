# Facial Landmark detection

This is a CI/CD example of an evaluation report produced by `giskard-vision` which compares a set of facial landmark detection models based on the following criteria:

- Performance on partial and entire facial parts
- Performance on images containing faces with different head poses (estimated with `6DRepNet`: https://github.com/thohemp/6DRepNet)
- Performance on images containing people from different ethnicities (estimated with `DeepFace`: https://github.com/serengil/deepface)
- Robustness against image perturbations like blurring, resizing, recoloring (performed by `opencv`: https://github.com/opencv/opencv)

Here're the results of the latest run:
|    | model   | facial_part   | dataloader                                                       |   prediction_time |   prediction_fail_rate | test     | metric   |   metric_value |   threshold | passed   |
|---:|:--------|:--------------|:-----------------------------------------------------------------|------------------:|-----------------------:|:---------|:---------|---------------:|------------:|:---------|
|  0 | OpenCV  | left half     | 300W cropped on left half                                        |           2.39632 |               0.564706 | TestDiff | NME_mean |      0.644057  |        -0.1 | False    |
|  1 | OpenCV  | upper half    | 300W cropped on upper half                                       |           2.4044  |               0.682353 | TestDiff | NME_mean |     -0.0402161 |        -0.1 | False    |
|  2 | OpenCV  | entire face   | 300W resizing with ratios: 0.5                                   |           2.43879 |               0        | TestDiff | NME_mean |      0.079876  |        -0.1 | False    |
|  3 | OpenCV  | entire face   | 300W altered with color mode 7                                   |           3.54933 |               0        | TestDiff | NME_mean |     -0.0013471 |        -0.1 | False    |
|  4 | OpenCV  | entire face   | 300W blurred                                                     |           3.32499 |               0        | TestDiff | NME_mean |      0.103017  |        -0.1 | False    |
|  5 | OpenCV  | entire face   | (Cached (300W) with head-pose) filtered using 'positive_roll'    |           1.95433 |               0        | TestDiff | NME_mean |     -0.0779265 |        -0.1 | False    |
|  6 | OpenCV  | entire face   | (Cached (300W) with head-pose) filtered using 'negative_roll'    |           3.39681 |               0        | TestDiff | NME_mean |      0.0194816 |        -0.1 | False    |
|  7 | OpenCV  | entire face   | (Cached (300W) with ethnicity) filtered using 'white_ethnicity'  |           3.22077 |               0        | TestDiff | NME_mean |     -0.196134  |        -0.1 | True     |
|  8 | OpenCV  | entire face   | (Cached (300W) with ethnicity) filtered using 'latino_ethnicity' |           2.1119  |               0        | TestDiff | NME_mean |      0.784538  |        -0.1 | False    |