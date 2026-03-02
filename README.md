I compile this script to fill my spare time while on standby due to the tense situation in Persian Gulf region, and this simple script may be useful un the future

This is a lightweight, high-precision web application for converting coordinates between **Grid (UTM)** and **Geographic (Latitude/Longitude)** systems on the WGS84 ellipsoid. 

Built for surveyors, geomatics engineers, and GIS professionals, this tool runs entirely locally in your browser—no server required. It utilizes `proj4js` for coordinate transformations and implements Redfearn's formulas to calculate **Grid Convergence** and **Point Scale Factor**.

## ✨ Features

* **Bi-directional Conversion:** Seamlessly convert from UTM to Geographic and vice versa.
* **Geodetic Parameters:** Automatically calculates Grid Convergence (in Decimal Degrees) and Point Scale Factor for every converted point.
* **Smart DMS Parser:** Flexibly input Degrees, Minutes, Seconds. The smart text parser understands multiple formats (e.g., `24 58 20 N`, `24°58'20"N`, or even `-24.97222`).
* **Batch File Processing:** Process thousands of points at once by uploading a CSV or TXT file. Preview the first 50 results and download the complete calculated data as a new CSV.
* **Client-Side Only:** Fast, secure, and works offline once loaded.

## 🚀 How to Use

Simply download or clone this repository and open `index.html` in any modern web browser (Chrome, Firefox, Edge, Safari). No installation, Node.js, or server setup is required.

### 1. Single Point Conversion

Navigate to the respective tabs ("Grid to Geographic" or "Geographic to Grid"), input your coordinates, and click **Calculate**. The app will display the resulting coordinates alongside the Grid Convergence and Scale Factor.

### 2. Batch Processing

Navigate to the **📂 Batch File Processing** tab. 

**For UTM to Geographic conversion**, prepare your CSV/TXT file with the following column format (comma-separated):

> `Zone, Point Name, Easting, Northing`  
> *Example:* `40N, GP01, 303757.851, 2763291.305`

**For Geographic to UTM conversion**, use this format:

> `Point Name, Latitude, Longitude`  
> *Example (Decimal):* `PT02, 24.97234, 55.05594`  
> *Example (DMS):* `PT03, 24 58 20 N, 55 03 21 E`

Click **Process File** to calculate, and then click **Download Output CSV** to save your results.

## 🛠️ Tech Stack

* **HTML5 / CSS3**
* **Vanilla JavaScript**
* **Bootstrap 5** (via CDN for responsive UI)
* **[Proj4js](http://proj4js.org/)** (via CDN for accurate geodetic transformations)

## 📝 Mathematical Reference

While coordinate X/Y transformations are handled by Proj4js, the **Grid Convergence** ($\gamma$) and **Point Scale Factor** ($k$) are calculated using Transverse Mercator series expansions (often associated with Krueger/Redfearn formulas) for high accuracy within standard UTM zones.
