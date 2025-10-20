## CT-DImQ-NPS

**CT-DImQ-NPS** is a Python-based **interactive GUI** that allows the user to calculate Noise Power Spectrum (NPS) on any CT DICOM dataset. This app is part of the **CT-DImQ** family of CT image quality assessment tools.

Created by Ainur K.


### Citation

If you use the codes in this repository or dataset, please cite:

### Getting started

#### Installation

Check out the [releases]([https://github.com/AK-CT-2025/CT-DImQ-NPS/releases](https://github.com/AK-CT-2025/CT-DImQ-CT-Image-quality-analysis-tools/releases)) of this repository. Find the latest release for NPS and download either `.app` file for MacOS or `.exe` file for Windows.

> [!NOTE]
> **Mac users** might encounter an **"unidentified developer"** error that stops the app from launching. If this occurs, follow these steps: <br/>
> 1. Open System Settings
> 2. Click Privacy & Security, scroll down and click the "Open Anyway" button.
> 3. The warning prompt reappears and click "Open".<br/>
> The app will now be saved as an exception, and the app will launch when opened again.

When launched, the app looks like this:
![Screenshot of the app when launched]([https://github.com/AK-CT-2025/CT-DImQ-NPS/blob/9084febaec7cba916f524493c07a95cc880ccc5d/readme_images/mac_opened-app_screenshot.png](https://github.com/AK-CT-2025/CT-DImQ-CT-Image-quality-analysis-tools/blob/0df043c879485de07a7c916795fbd1dba58bc376/readme%20images/NPS/macos_CT-DImQ-NPS_screenshot.png)

#### Use case example
As a use case example of CT-DImQ-NPS, you can perform analysis on the provided CT anthropomorphic phantom data, from the [link](https://github.com/AK-CT-2025/CT_datasets.git) (CATPHAN phantom scanned under clinical conditions at 1.7 mGy dose level, reconstructed with Filtered-Back-Projection (FBP) and iterative (IR) reconstruction algorithms).

Here is the screenshot of the app from sample NPS analysis on FBP data: ![Screenshot of the app: sample NPS analysis]([https://github.com/AK-CT-2025/CT-DImQ-NPS/blob/9084febaec7cba916f524493c07a95cc880ccc5d/readme_images/macos_CT-DImQ-NPS_screenshot.png](https://github.com/AK-CT-2025/CT-DImQ-CT-Image-quality-analysis-tools/blob/0df043c879485de07a7c916795fbd1dba58bc376/readme%20images/NPS/macos_CT-DImQ-NPS_screenshot.png)

To get the result above, follow these steps:
1. Click "Import files:" and select `FBP` folder from `CTDIvol_1.7mGy_FC18` dataset. There are multiple subfolders inside `FBP` which correspond to repeated acquisitions. These subfolders appear in the drop-down menu next to "Import files:" button.
2. The user is expected to provide `Slice start` and `Slice end` values. These values specify the range of slices upon which the mean signal is calculated. This mean signal is subtracted from the image slices to remove low-frequency components in the image. In this example, `Slice start` is 35, `Slice end` is 80.
> [!IMPORTANT]
> Python uses zero-based indexing, therefore the first slice is numbered as 0 (not 1).
3. Region of Interest (ROI) for calculation of NPS can be specified by drawing a rectangle or ellipse  with the mouse or manually inputting the coordinates. In this example, the ROI is drawn on `Slice 35` , `X: 216, Y: 218, W: 80, H: 80`. 
> [!NOTE]
> For users familiar with **ImageJ** or **Fiji** software: Manual input of coordinates is the same as in ImageJ/Fiji, but with an offset of one index due to differing indexing conventions between Python (zero-based indexing) and ImageJ (one-based indexing).

4. Clicking "Apply ROI" button will show the specified ROI on the bottom left. NPS can be calculated on the specified slice by clicking "Calculate NPS from Applied ROI". NPS can also be calculated across slices using the drawn ROI by clicking "Calculate NPS across slices" button. This will prompt the user to specify the range across which NPS is to be calculated by inputting slice start and slice end values. In this example, slice start was 35 and slice end was 80.
5.  Calculated 2D NPS and 1D NPS appear on the screen.



