# Report-Analysis-teamwork-quiz
This is a repository created to visualize into a Report PDF the answer provided during a quiz made for improve teamworking in a general company


## Overview

This project generates a PDF report from session data, including total scores and response times of teams. The report includes visualizations created from XML data files and a logo image.

## Requirements

To run this project, you need the following Python packages:

- `reportlab` - For generating the PDF report.
- `Pillow` (PIL) - For image processing.
- `matplotlib` - For creating plots.
- `pandas` - For data manipulation.
- `xml.etree.ElementTree` - For parsing XML files.
- `io` - For handling in-memory byte streams.
- `glob` - For file path matching.

You can install these packages using pip:

pip install reportlab Pillow matplotlib pandas

## Project Structure

1. **XML Files**:
   - **Location**: `sessione_test/`
   - **Filenames**: `SESSIONE *.xml`
   - Description: These XML files should contain the session data including teams and questions.

2. **Logo Image**:
   - **Location**: `thinkbey_logo/`
   - **Filename**: `Think01_nero.png`
   - Description: This image is used as the logo in the PDF report.

3. **Output**:
   - **Filename**: `report_totale.pdf`
   - Description: The generated report will be saved as `report_totale.pdf` in the current working directory.

## Usage

### 1. Prepare XML Files

Ensure that the XML files are located in the `sessione_test/` directory. The filenames should match the pattern `SESSIONE *.xml`, and the XML structure should include the relevant `teams` and `questions` elements.

### 2. Prepare Logo Image

Place the logo image `Think01_nero.png` in the `thinkbey_logo/` directory. The image should be in PNG format with transparency if required.

### 3. Run the Script

Execute the Python script containing the code provided. This will process the XML files, generate plots, and create the PDF report.

## Code Explanation

### Image Processing

The script opens and processes the logo image to ensure it has an RGBA mode, preserving transparency. If the image is not already in RGBA mode, it is converted to this mode before saving.

### XML Parsing

The script parses XML files to extract team scores and question responses. Each XML file is read and processed to create a list of dictionaries for teams and questions. The data is then converted into Pandas DataFrames for further analysis.

- **Teams**: Each team’s name, score, and time used are extracted.
- **Questions**: Each question’s text, correct answer, and responses from various teams are extracted.

### Plot Generation

Two types of bar plots are generated:

1. **Total Scores**: Displays the total score for each team. The highest score is highlighted in red, and an average line is drawn in gray for reference.

2. **Response Times**: Shows the total time used by each team. Similar to the scores plot, the highest value is highlighted in red, and an average line is included.

### PDF Generation

The `reportlab` library is used to create a PDF report that includes:

- **Title**: The title of the report.
- **Logo**: The logo image placed at the top of the report.
- **Plots**: The generated plots for total scores and response times.

The report is formatted with appropriate titles, plot placements, and dimensions to ensure a professional presentation.

## Troubleshooting

- **Missing Files**: Ensure that all necessary XML files and the logo image are correctly placed in their respective directories. The XML files should be in the `sessione_test/` directory, and the logo image should be in the `thinkbey_logo/` directory.

- **File Not Found Errors**: Verify that the paths specified in the script match the actual locations of your files. Double-check the filenames and directory names to ensure they are correct.

- **Plot Generation Issues**: Make sure `matplotlib` is correctly installed. You can reinstall it using `pip` if necessary. If you encounter issues with plot generation, review the code to ensure that the plot generation logic is functioning as expected.

## License

## Acknowledgements

- The `reportlab` and `matplotlib` libraries for PDF and plot generation.
- The `Pillow` library for image processing.
