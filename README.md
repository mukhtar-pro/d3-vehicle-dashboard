<!-- omit from toc -->
# Real-Time Electric Vehicles Monitoring Dashboard with D3.js

A modern, interactive dashboard for monitoring electric vehicle data across the United States, built with D3.js. Features a sleek dark mode interface and real-time data visualization capabilities.

<!-- omit from toc -->
## Index

- [Introduction](#introduction)
- [Setup](#setup)
- [Architecture](#architecture)
  - [Directory Structure](#directory-structure)
  - [Data Processing](#data-processing)
  - [Event Handling](#event-handling)
  - [Charts](#charts)
  - [Styling](#styling)
  - [HTML Structure](#html-structure)
- [Features](#features)

---

## Introduction

As part of our university coursework, we were tasked with designing and developing an interactive visualization application for the dataset of our choice, using HTML, CSS, JavaScript, and the [D3.js](https://d3js.org/) library.

The dataset we chose for this project is the [Electric Vehicles Population Dataset](https://www.kaggle.com/datasets/yashusinghal/electric-vehicle-population-dataset), a publicly available Kaggle dataset that contains information about electric vehicles (EVs) in the United States of America (USA).<br>
It includes data such as the Make, Model, State, Electric Vehicle Type, and the Electric Range of the vehicles.

## Setup

This setup guide is primarily for users of [Visual Studio Code](https://code.visualstudio.com/). If you're using a different code editor, ensure you have a local web server package like [XAMPP](https://www.apachefriends.org/) installed.

Ensure the following are installed on your machine:

- [Visual Studio Code](https://code.visualstudio.com/)
- [Git](https://git-scm.com/)

To set up the application:

1. Clone the repository: `git clone https://gitlab-student.macs.hw.ac.uk/cr2007/f20dv-group-project`. Alternatively, download the ZIP file from the "Code" button.
2. Open the project in Visual Studio Code.
3. Install the recommended extensions in [`.vscode/extensions.json`](./.vscode/extensions.json). Ensure the Live Server extension is installed.
4. Open `index.html` and click "**Go Live**" to run the application on a local server.
5. The application will open in your default web browser at [`http://localhost:5500`](http://localhost:5500).
6. Interact with the application and view the visualizations.
7. Changes to the code will reflect in the browser in real-time.

## Architecture

<div align="center">
  <img src="images/Application_Architecture.png" width="60%"/>
</div>

The application is a modern data visualization dashboard for electric vehicle data. It uses [D3.js](https://d3js.org/) for creating various types of charts and vanilla JavaScript for data processing and event handling. The application features a sleek dark mode interface and is styled using modern CSS practices.

### Directory Structure

The project is structured as follows:

- [`data/`](./data/): Constains the [CSV data file](./data/Electric_Vehicle_Population_Data_Cleaned.csv) used for generating the charts.
- [`lib/`](./lib/): Contains the D3.js library file [`d3.v7.min.js`](./lib/d3/d3.v7.min.js)
- [`scripts/`](scripts/): Constains JavaScript file s for each type of chart, connected by the main script file:
  - [`main.js`](./scripts/main.js): Handles data loading, processing, and event handling
  - [`barChart.js`](./scripts/barChart.js): Implementation of the Bar Chart
  - [`pieChart.js`](./scripts/pieChart.js): Implementation of the Pie Chart
  - [`stackedBarChart.js`](./scripts/stackedBarChart.js): Implementation the Stacked Bar Chart
  - [`lineChart.js`](./scripts/lineChart.js): Implementation of the Line Chart
  - [`scatterPlot.js`](./scripts/scatterPlot.js): Implementation of the Scatter Plot
  - [`groupedChart.js`](./scripts/groupedChart.js): Implementation of the Grouped Bar Chart
  - [`map.js`](./scripts/map.js): Implementation of the Map Chart
  - [`helper.js`](./scripts/helper.js): Reusable functions that have been used throughout the development of the charts
- [`styles/`](./styles/): Contains CSS files for each type of chart and the [main CSS file](./styles/main.css):
  - [`main.css`](./styles/main.css): Contains the main style and imports other CSS files
- [`index.html`](./index.html): The main HTML file that includes the D3.js library, the main CSS file and placeholders for the charts

---

### Data Processing

The CSV data is loaded and processed in `main.js` via the [`d3.csv()`](https://d3js.org/d3-fetch#csv) function.

The data processing functions transform the raw data into a format suitable for each type of chart.<br>
The processed data is then passed to the corresponding chart's render function.

### Event Handling

The event handling is also done in the [`main.js`](./scripts/main.js) file.

For example, it includes an event listener for the search input field.<br>
When the user types in the search input field, the data is filtered based on the search query and the charts are updated accordingly.

### Charts

Each chart is implemented as a class in its own JavaScript file.

The classes include a `render` function that takes the processed data and generates the chart.

### Styling

The application uses a modern CSS architecture with CSS variables for theming. The [main CSS file](./styles/main.css) includes:

- Dark mode support with smooth transitions
- CSS variables for consistent theming
- Modern layout using CSS Grid
- Responsive design principles
- Card-based UI components

The dark mode can be toggled using a button in the top-right corner of the application.

### HTML Structure

The [main HTML file](./index.html) includes the D3.js library, the main CSS file, and placeholders for the charts.

The placeholders are `div` elements with specific IDs corresponding to each type of chart.

## Features

- 📊 Interactive D3.js visualizations
- 🌙 Modern dark mode interface
- 🔍 Real-time data filtering
- 🗺️ Geographic data visualization
- 📱 Responsive design
- ⚡ Performance optimized

---
