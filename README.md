# Facial Landmark detection

This is a CI/CD example of an evaluation report produced by `giskard-vision` which compares a set of facial landmark detection models based on the following criteria:

- Performance on partial and entire facial parts
- Performance on images containing faces with different head poses (estimated with `6DRepNet`: https://github.com/thohemp/6DRepNet)
- Performance on images containing people from different ethnicities (estimated with `DeepFace`: https://github.com/serengil/deepface)
- Robustness against image perturbations like blurring, resizing, recoloring (performed by `opencv`: https://github.com/opencv/opencv)

## Summary of the latest run:
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="3" halign="left">Best(prediction_time)</th>
      <th colspan="3" halign="left">Best(prediction_fail_rate)</th>
      <th colspan="3" halign="left">Best(metric_value)</th>
    </tr>
    <tr>
      <th>model</th>
      <th>FaceAlignment</th>
      <th>Mediapipe</th>
      <th>OpenCV</th>
      <th>FaceAlignment</th>
      <th>Mediapipe</th>
      <th>OpenCV</th>
      <th>FaceAlignment</th>
      <th>Mediapipe</th>
      <th>OpenCV</th>
    </tr>
    <tr>
      <th>criteria</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>altered color</th>
      <td></td>
      <td>✓</td>
      <td></td>
      <td>✓</td>
      <td></td>
      <td></td>
      <td></td>
      <td>✓</td>
      <td></td>
    </tr>
    <tr>
      <th>blurred</th>
      <td></td>
      <td>✓</td>
      <td></td>
      <td>✓</td>
      <td></td>
      <td></td>
      <td>✓</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th>cropped on left half</th>
      <td></td>
      <td>✓</td>
      <td></td>
      <td>✓</td>
      <td></td>
      <td></td>
      <td>✓</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th>cropped on upper half</th>
      <td></td>
      <td>✓</td>
      <td></td>
      <td>✓</td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>✓</td>
    </tr>
    <tr>
      <th>latino_ethnicity</th>
      <td></td>
      <td>✓</td>
      <td></td>
      <td></td>
      <td></td>
      <td>✓</td>
      <td></td>
      <td></td>
      <td>✓</td>
    </tr>
    <tr>
      <th>negative_roll</th>
      <td></td>
      <td>✓</td>
      <td></td>
      <td>✓</td>
      <td></td>
      <td></td>
      <td>✓</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th>positive_roll</th>
      <td></td>
      <td>✓</td>
      <td></td>
      <td>✓</td>
      <td></td>
      <td></td>
      <td></td>
      <td>✓</td>
      <td></td>
    </tr>
    <tr>
      <th>resized with ratios: 0.5</th>
      <td></td>
      <td>✓</td>
      <td></td>
      <td>✓</td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>✓</td>
    </tr>
    <tr>
      <th>white_ethnicity</th>
      <td></td>
      <td>✓</td>
      <td></td>
      <td>✓</td>
      <td></td>
      <td></td>
      <td>✓</td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>
## Full Report
|    | criteria                 | model         | test     | metric   |   metric_value | Best(metric_value)   |   prediction_time | Best(prediction_time)   |   prediction_fail_rate | Best(prediction_fail_rate)   |
|---:|:-------------------------|:--------------|:---------|:---------|---------------:|:---------------------|------------------:|:------------------------|-----------------------:|:-----------------------------|
|  0 | altered color            | FaceAlignment | TestDiff | NME_mean |     -0.186222  |                      |         105.953   |                         |              0.02      | ✓                            |
|  1 | altered color            | Mediapipe     | TestDiff | NME_mean |     -0.219791  | ✓                    |           8.50774 | ✓                       |              0.79      |                              |
|  2 | altered color            | OpenCV        | TestDiff | NME_mean |      0.244796  |                      |          54.6167  |                         |              0.14      |                              |
|  3 | blurred                  | FaceAlignment | TestDiff | NME_mean |     -0.0451077 | ✓                    |         110.126   |                         |              0.04      | ✓                            |
|  4 | blurred                  | Mediapipe     | TestDiff | NME_mean |      0.0566332 |                      |          10.0863  | ✓                       |              0.09      |                              |
|  5 | blurred                  | OpenCV        | TestDiff | NME_mean |      0.410555  |                      |          51.0361  |                         |              0.12      |                              |
|  6 | cropped on left half     | FaceAlignment | TestDiff | NME_mean |     -0.553663  | ✓                    |          80.2212  |                         |              0.820441  | ✓                            |
|  7 | cropped on left half     | Mediapipe     | TestDiff | NME_mean |     -0.170099  |                      |           8.53259 | ✓                       |              0.951029  |                              |
|  8 | cropped on left half     | OpenCV        | TestDiff | NME_mean |     -0.0978757 |                      |          38.5103  |                         |              0.825882  |                              |
|  9 | cropped on upper half    | FaceAlignment | TestDiff | NME_mean |     -0.541586  |                      |          75.6942  |                         |              0.782941  | ✓                            |
| 10 | cropped on upper half    | Mediapipe     | TestDiff | NME_mean |     -0.2261    |                      |           8.6209  | ✓                       |              0.941765  |                              |
| 11 | cropped on upper half    | OpenCV        | TestDiff | NME_mean |     -0.720575  | ✓                    |          37.681   |                         |              0.978824  |                              |
| 12 | latino_ethnicity         | FaceAlignment | TestDiff | NME_mean |      0.371225  |                      |          55.5234  |                         |              0.142857  |                              |
| 13 | latino_ethnicity         | Mediapipe     | TestDiff | NME_mean |      0.038642  |                      |           5.20922 | ✓                       |              0.285714  |                              |
| 14 | latino_ethnicity         | OpenCV        | TestDiff | NME_mean |     -0.66035   | ✓                    |          31.0707  |                         |              0         | ✓                            |
| 15 | negative_roll            | FaceAlignment | TestDiff | NME_mean |     -0.576123  | ✓                    |          75.4833  |                         |              0.0416667 | ✓                            |
| 16 | negative_roll            | Mediapipe     | TestDiff | NME_mean |     -0.0123974 |                      |           6.63929 | ✓                       |              0.0833333 |                              |
| 17 | negative_roll            | OpenCV        | TestDiff | NME_mean |     -0.386019  |                      |          37.9475  |                         |              0.125     |                              |
| 18 | positive_roll            | FaceAlignment | TestDiff | NME_mean |      0.54085   |                      |          79.7585  |                         |              0.0576923 | ✓                            |
| 19 | positive_roll            | Mediapipe     | TestDiff | NME_mean |      0.0147429 | ✓                    |           7.52416 | ✓                       |              0.288462  |                              |
| 20 | positive_roll            | OpenCV        | TestDiff | NME_mean |      0.505026  |                      |          44.0232  |                         |              0.192308  |                              |
| 21 | resized with ratios: 0.5 | FaceAlignment | TestDiff | NME_mean |      0.0185174 |                      |         105.43    |                         |              0.04      | ✓                            |
| 22 | resized with ratios: 0.5 | Mediapipe     | TestDiff | NME_mean |      0.0358656 |                      |           9.63136 | ✓                       |              0.12      |                              |
| 23 | resized with ratios: 0.5 | OpenCV        | TestDiff | NME_mean |     -0.0042923 | ✓                    |          37.8424  |                         |              0.18      |                              |
| 24 | white_ethnicity          | FaceAlignment | TestDiff | NME_mean |     -0.604868  | ✓                    |          78.9769  |                         |              0.0384615 | ✓                            |
| 25 | white_ethnicity          | Mediapipe     | TestDiff | NME_mean |      0.0260865 |                      |           7.46366 | ✓                       |              0.173077  |                              |
| 26 | white_ethnicity          | OpenCV        | TestDiff | NME_mean |     -0.495647  |                      |          42.1803  |                         |              0.0769231 |                              |