
# Interactive Dashboard for Bacteria Cultures

This project creates an interactive dashboard that visualizes bacterial cultures data from belly button samples. The dashboard allows users to select different samples and dynamically update charts and metadata related to the chosen sample.

## Project Overview

This dashboard consists of:

- **Metadata Panel**: Displays demographic information about the selected sample.
- **Bar Chart**: Shows the top 10 bacterial species (OTUs) found in the selected sample.
- **Bubble Chart**: Displays all bacterial species in the sample, where the size of the marker corresponds to the quantity of bacteria found.
- **Dropdown Menu**: Allows users to select a different sample ID to view updated data.

## Data Source

The data used in this project is loaded from the following JSON file:  
`https://static.bc-edx.com/data/dl-1-2/m14/lms/starter/samples.json`

The JSON file contains the following fields:

- `names`: Array of sample IDs.
- `metadata`: Demographic information of the samples.
- `samples`: Bacterial data including `otu_ids`, `otu_labels`, and `sample_values`.

## JavaScript Functions

### 1. `init()`
This function is executed when the page is loaded. It does the following:
- Loads the JSON data.
- Populates the dropdown menu with the list of sample IDs.
- Displays the first sample's metadata and charts on initial load.

### 2. `buildMetadata(sample)`
This function updates the metadata panel with demographic information for the selected sample. It:
- Fetches the sample's metadata from the JSON data.
- Dynamically updates the panel with key-value pairs using D3.

### 3. `buildCharts(sample)`
This function creates the bar and bubble charts for the selected sample. It:
- Filters the data to find the sample's OTU IDs, OTU labels, and sample values.
- Constructs a bubble chart that displays all OTUs for the sample.
- Constructs a bar chart that displays the top 10 OTUs.

### 4. `optionChanged(newSample)`
This function is triggered when a new sample is selected from the dropdown menu. It:
- Calls `buildCharts(newSample)` and `buildMetadata(newSample)` to update the dashboard with the selected sample's data.

## Usage

1. **Clone the repository** or download the project files.
2. **Include the following libraries**:
    - D3.js for data binding and DOM manipulation.
    - Plotly.js for chart rendering.

3. Ensure the JSON file is accessible through the provided URL.
4. Open the `index.html` file in a web browser to view the interactive dashboard.

## Example Workflow

1. Upon loading, the first sample's data will be displayed.
2. Use the dropdown menu to select a different sample.
3. The charts and metadata will automatically update based on the selected sample.

## File Structure

```
.
├── index.html         # Main HTML file
├── app.js             # JavaScript file with D3 and Plotly functionality
├── README.md          # Project documentation (this file)
└── samples.json       # Data (loaded from URL)
```

## Charts

### Bubble Chart

- **X-axis**: OTU IDs
- **Y-axis**: Sample values (quantities of bacteria)
- **Marker Size**: Corresponds to the sample values
- **Marker Color**: Represents OTU IDs
- **Hover Text**: OTU labels (bacterial names)

### Bar Chart

- **X-axis**: Sample values of the top 10 OTUs
- **Y-axis**: Corresponding OTU IDs
- **Orientation**: Horizontal bar chart