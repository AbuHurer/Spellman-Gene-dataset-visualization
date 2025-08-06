# Interactive Genomics ML Pipeline

An **interactive, browser-based web application** that demonstrates a complete, simplified machine learning pipeline for clustering gene expression data. Easily upload your data, cluster with K-Means, and explore results in interactive 3D!

---

## 🔬 Features

- **CSV File Upload:** Upload your own gene expression data in CSV format.
- **Automated ML Pipeline:** Guided 4-step workflow—
    1. **Data Acquisition:** Load data from a local file.
    2. **Preprocessing:** Automatic Z-score (standard) normalization.
    3. **ML Model Training:** K-Means clustering algorithm.
    4. **Visualization:** Interactive 3D plot of results.
- **Customizable K-Means:** Select desired number of clusters (k).
- **Interactive 3D Visualization:**
    - Starts with a 3D DNA helix to set the genomics theme.
    - Plots each gene as a point in a 3D space, color-coded by cluster.
    - 3D view supports rotation and zoom.
- **Responsive UI:** Clean, modern design using Tailwind CSS.
- **No Backend Needed:** 100% client-side; all logic in a single `index.html`.

---

## ⚙️ Pipeline Flow

1. **Data Acquisition**
    - Upload a CSV file using the interface.
    - FileReader API parses the data, skipping header and extracting gene names and expression values.
2. **Preprocessing (Standardization)**
    - For each gene (row), compute mean (μ) and standard deviation (σ) of expression values.
    - Normalize values:
    - Ensures features are comparable for K-Means.
3. **K-Means Clustering**
    - User-selected *k* value.
    - Runs a K-Means algorithm (JavaScript) to group genes by expression patterns.
4. **3D Visualization**
    - For each gene, first three normalized values become X, Y, Z coordinates.
    - Genes colored by cluster.
    - Intuitive 3D view: rotate/zoom with mouse.

---

## 💻 Technology Stack

| Layer       | Technology                  |
|-------------|----------------------------|
| Frontend    | HTML5, CSS3, JavaScript    |
| Styling     | [Tailwind CSS](https://tailwindcss.com/)          |
| 3D Graphics | [Three.js](https://threejs.org/)                 |

---

## 🚀 How to Run Locally

**Prerequisites:**
- [Visual Studio Code](https://code.visualstudio.com/)
- [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)

**Steps:**
1. **Save the Code:** Create a folder (e.g., `genomics-pipeline`) and save `index.html` inside.
2. **Open in VS Code:** Open the folder in VS Code.
3. **Start the Server:** Right-click `index.html` → *Open with Live Server*.
4. **View in Browser:** The app opens automatically in your browser.

---

## 📊 CSV Data Format

- **First row**: Header (skipped)
- **First column**: Gene name (e.g., `YAL001C`)
- **Remaining columns**: Numeric expression values

**Example:**
```
GeneName,Time1,Time2,Time3,Time4
YAL001C,-0.07,-0.23,-0.1,0.03
YAL014C,0.215,0.09,0.025,-0.04
YAL016W,0.15,0.15,0.22,0.29
```

---

## 🔮 Planned Future Improvements

- **Dimensionality Reduction:** Implement PCA for more accurate 2D/3D plots.
- **Additional Clustering:** Hierarchical Clustering, DBSCAN options.
- **Interactive Tooltips:** Show gene info on hover.
- **Export Results:** Download clusters as CSV.
- **Elbow Method:** Auto-suggest optimal k with inertia plot.

---
```
