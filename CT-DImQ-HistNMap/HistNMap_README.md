## CT-DImQ-HistNMap
**CT-DImQ-HistNMap**: is a Python-based **interactive GUI** that allows the user to evaluate distribution of CT values through histogram analysis and noise maps. This app is part of the **CT-DImQ** family of CT image quality assessment tools.

Created by Ainur K.

### Citation
If you use the codes in this repository or dataset, please cite:

### Getting started

#### Installation
Check out the [releases]([https://github.com/AK-CT-2025/CT-DImQ-HistNMap/releases](https://github.com/AK-CT-2025/CT-DImQ-CT-Image-quality-analysis-tools/releases)) of this repository. Find the latest release for HistNMap and download either `.app` file for MacOS or `.exe` file for Windows. 

> [!NOTE]
>**Mac users** might encounter an **"unidentified developer"** error that stops the app from launching. If this occurs, follow these steps: <br/>
>1. Open System Settings
>2. Click Privacy & Security, scroll down and click the "Open Anyway" button.
>3. The warning prompt reappears and click "Open".<br/>
>The app will now be saved as an exception, and the app will launch when opened again.


When launched, the app looks like this:
![Screenshot of the app when launched](https://github.com/AK-CT-2025/CT-DImQ-CT-Image-quality-analysis-tools/blob/0ae89b9a2a7fae8e710f556cc0ceb9e1a51c0d74/readme%20images/HistNMap/launch.png)

The app has two layouts: left layout **"ROI controls"** for ROI selection and image controls, and right layout made of two tabs: **“Applied ROI Histogram”** and **“Noise map”**.
The user can import any folder(s) containing CT DICOM slices.


#### Use case example
As a use case example of CT-DImQ-NPS, you can perform analysis on the provided CT anthropomorphic phantom data, from the [link]([https://github.com/AK-CT-2025/CT_datasets.git](https://github.com/AK-CT-2025/CT-DImQ-CT-Image-quality-analysis-tools/tree/0ecfd6ed49d45b035644763c0e0f919c420cfbdf/Dataset/3D-printed_lung_phantom)) (3D-printed thorax phantom scanned under clinical conditions at 2.6 mGy dose level, reconstructed with Iterative Reconstruction (IR) and Deep-Learning Reconstruction (DLR)).

<video src="https://github.com/AK-CT-2025/CT-DImQ-HistNMap/blob/c8165e8ec22950b0ba64bbd4be1123187fc8af69/readme%20images/screen%20recording%20HistNMap.mp4" width="320" height="240" controls></video>


#### ROI controller
The central slice of the image stack will be displayed by default. The user can change slices and select ROI with interactive sliders and a manual input fields. **"Display mode"** controls the image adjustment, which can be done either by thresholding ("Threshold") or by adjusting window level and width ("Window/Level"). When "Threshold" mode is selected, "Window Level" and "Window Width" controls are inactive, and vice versa.

Cropped ROI is displayed on "Applied ROI Histogram" tab.

Histogram below the ROI controller shows distribution of CT values of displayed image slice.

#### Applied ROI Histogram tab
ROI image can be exported as TIFF file.

Histogram of CT values within the ROI is shown at the bottom of the tab. 
User can obtain histogram of ROI across slices by clicking "Get histogram across slices" button.

![Applied ROI Histogram](https://github.com/AK-CT-2025/CT-DImQ-CT-Image-quality-analysis-tools/blob/0ae89b9a2a7fae8e710f556cc0ceb9e1a51c0d74/readme%20images/HistNMap/ROI%20histogram.png)

#### Noise map
The tab contains a box which shows the names of all imported folders, allowing the user to select folders for noise map generation. These folders are assumed to be repeated acquisitions without phantom movement. The noise map is calculated by calculating the standard deviation of each pixel value across the selected folders. 

The user can adjust the window width and level, and export the noise map as a TIFF file into a specified directory. Noise distribution is also shown on the histogram which can be calculated across slices and exported as excel file. 

Noise map image and its histogram work in tandem with the “Apply ROI” button in the “ROI controller”.

![Noise map](https://github.com/AK-CT-2025/CT-DImQ-CT-Image-quality-analysis-tools/blob/0ae89b9a2a7fae8e710f556cc0ceb9e1a51c0d74/readme%20images/HistNMap/noise%20map.png)
