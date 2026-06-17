# Straight-Beam-Piezo-Actuator-FEA
Finite Element Analysis model for phase-difference optimization in straight-beam traveling-wave piezoelectric actuators.

# Phase-Difference Optimization for Beam-Type Piezoelectric Actuators

This repository provides the complete Finite Element Analysis (FEA) source files used in our study to investigate and optimize the traveling wave quality in straight-beam piezoelectric actuators. By open-sourcing these models, we aim to ensure the absolute transparency and reproducibility of our computational results.

## 📥 Download Link
Due to the large size of the ANSYS result files, the complete project has been uploaded to Baidu Netdisk (free to download).
- **Download Link:** https://pan.baidu.com/s/13dnMMPvHhC226zIZb2vuKA?pwd=1436 
- **Extraction Code:** [1436]

*(Note: Please ensure that the `.wbpj` file and the `_files` folder are kept in the same directory after downloading.)*

## 📂 File Description
The package contains the main ANSYS Workbench project and three interchangeable 3D geometry files (Parasolid `.x_t` format) to verify the generalizability of the proposed method across different structural designs:
- `2Jchangfangxing.wbpj`: The main ANSYS Workbench project file.
- `Stepwise beam.x_t`: The geometry for the stepped beam **(Loaded as the default model)**.
- `changfangxing.x_t` (Flat beam): The geometry for the standard flat straight beam.
- `Arc-shaped beam.x_t`: The geometry for the arc-shaped beam.

## ⚙️ Software Requirements
- **ANSYS Version**: ANSYS 2021 R1 (or newer versions).

## 🚀 Step-by-Step Usage Guide

To reproduce the results presented in our manuscript, please follow this standard workflow:

### Step 1: Change the Geometry (Optional)
The default project is set up for the **Stepwise beam**. To test other configurations:
1. Open `2Jchangfangxing.wbpj` in ANSYS Workbench.
2. Right-click on the `Geometry` cell in the project schematic.
3. Select `Replace Geometry` -> `Browse...` and choose either `changfangxing.x_t` or `Arc-shaped beam.x_t`.
4. Update the mesh in the `Mechanical` module.

### Step 2: Modal Analysis (Crucial First Step)
Because changing the boundary stiffness or geometry shifts the system's natural frequency, you must find the new resonant working point first:
1. Open the `Modal` analysis module.
2. Click **Solve** to extract the natural frequencies.
3. Identify the target bending mode frequency (e.g., B04 mode) from the results.

### Step 3: Harmonic Response & Phase Adjustment
1. Open the `Harmonic Response` module.
2. Update the excitation `Frequency` to the exact resonant frequency obtained in Step 2.
3. **Adjusting the Phase Difference:** Under the piezoelectric body boundary conditions, select the applied `Voltage`. You can adjust the phase difference between the driving phases by modifying the **Real** and **Imaginary** parts of the voltage inputs. 
   *(For example, to set a specific phase angle $\theta$, set Real = $V_0 \cos\theta$ and Imaginary = $V_0 \sin\theta$).*
4. Click **Solve**.
5. Evaluate the spatial amplitude distribution, Coefficient of Variation (CV), and Traveling Wave Ratio (TWR) along the measurement points.

## 📊 Key Findings Reproducible in this Model
- The traditional $90^\circ$ phase difference induces severe standing waves due to boundary reflections.
- Adjusting the phase difference (e.g., to $80^\circ$) significantly suppresses the reflected waves

- ## 📝 Citation

If you find this repository useful or inspiring for your research, please consider citing our work. 

**Note:** The paper is currently under review. The specific citation details (Journal name, Volume, DOI, etc.) will be updated here immediately once the paper is officially published.

