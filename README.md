# Python-code-for-XRD-plot
A simple and customizable Python script to generate publication-quality XRD (X-ray Diffraction) plots from .csv data. This script automatically annotates specified peaks and is optimized for a clean, scientific aesthetic.

(Note: You must run the script once to generate this XRD_TiO2_Anatase_Plot.png image, then commit and push it to your repository for it to appear here.)

**Features**

Reads CSV Data: Directly plots from a two-column .csv file (2-Theta and Intensity).

Peak Annotation: Automatically finds and labels specified (hkl) peaks.

Vertical Labels: Annotations are rotated 90 degrees for clarity.

Clean Aesthetics:

Removes y-axis numerical labels for an "arbitrary units" look.

Uses high-quality Arial font.

Includes inward-facing ticks, common in scientific publications.

High-Resolution Output: Saves plots as 300-dpi .png files suitable for publication.

**Installation**

Clone this repository to your local machine:

Install the required Python libraries:

**How to Use**

Place your data file (e.g., My_Data.csv) in the repository folder.

Open XRD_Plotter.py in a text editor.

Change the your_csv_filename variable to point to your file:

your_csv_filename = "My_Data.csv"


(Optional) Change the output_filename variable:

output_filename = "My_Plot.png"


Run the script from your terminal:

python XRD_Plotter.py


Your new plot will be saved as My_Plot.png in the same folder.

**Customization**

This script is designed to be easily customized inside the plot_publishable_xrd function.

1. How to Change Peak Annotations

Modify the anatase_peaks list. Add, remove, or edit the 2-theta values and (hkl) labels for your specific material.

# --- 1. Define Standard Peaks to Label ---
anatase_peaks = [
    (25.303, '(101)'),
    (37.792, '(004)'),
    (48.035, '(200)'),
    # ... add your other peaks here
]


2. How to Change Plot Style (Line Color, Width, Symbols)

Find the ax.plot line and modify its parameters.

# --- 4. Plot the Data ---

# Original:
ax.plot(two_theta, intensity, color='black', linewidth=1.5)

# Example (Blue dashed line with circle markers):
ax.plot(
    two_theta,
    intensity,
    color='blue',
    linewidth=1.0,
    linestyle='--',
    marker='o',
    markersize=3,
    markevery=100 # Only show every 100th marker
)


3. How to Change Figure Size or Background Color

Modify the plt.subplots call or rcParams.

# --- 3. Set Up the Plot Aesthetics ---

# Change figure size (width, height in inches)
fig, ax = plt.subplots(figsize=(10, 6))

# Change plot area background color
ax.set_facecolor('#f5f5f5')


4. How to Change Annotation Style (Size, Color, Rotation)

Find the ax.annotate call and modify its parameters.

# --- 5. Annotate the Peaks ---
ax.annotate(
    hkl_label,
    # ...
    fontsize=10,         # Change font size
    rotation=45,         # Change rotation (0 = horizontal)
    color='darkred',     # Change text color
    arrowprops=dict(
        arrowstyle="-",
        color='darkred'  # Change arrow color
    )
)


Citation

If you use this code in your research, please consider citing:
1.	AA Haidry*, Yucheng Wang, Yanling Weng, Adil Raza, Kareem Yusuf, Excellent acetone sensing enabled by tunable metal organic framework derived TiO2 nanodisks, Talanta, 2025 127547
https://doi.org/10.1016/j.talanta.2025.127547
2.	Y Wang, AA Haidry*, A Raza, Z Wang, F Ghani, Y Weng, NH Alotaibi, Enhancing humidity sensing performance through structural and catalytic optimization in platinum-modified ordered mesoporous titania, Applied Surface Science, Volume 662, 30 July 2024, 160113. https://doi.org/10.1016/j.apsusc.2024.160113
3.	14.	AA Haidry*, Q. Fatima, Z. Wang, Y. Wang, Y. Ji, and A. Raza, Optimization of the specific surface area of ordered mesoporous TiO2 yields a high response to humidity, Colloids and Surfaces: A Physicochemical Engineering Aspect, vol. 667, p. 131371, 2023. (Cover Image)
https://doi.org/10.1016/j.colsurfa.2023.131371

