Cutter-x-list
Blender add-on for creating and exporting cut lists for sheet material. Generates XLSX spreadsheets, PDF documents, and visual cutting diagrams directly from mesh objects in the scene.
Version: 1.0
Author: Tom StarSky
Blender: 4.5.0 or newer
Category: Generic

Features

Panel management: Create any number of sheet types with name, length, width, thickness, comment, and grain orientation (longitudinal/crosswise)
Material generation: Automatically create a Blender material per sheet that can then be assigned to mesh objects
XLSX export: Complete cut list with grouped quantities, plus an overview of required sheets (including a 4 mm saw kerf allowance)
PDF export: Cut list table as A4 landscape PDF (requires reportlab)
Cutting diagram (nesting): Visual PNG layout of sheet usage with labels for each part (requires Pillow)
Presets: Save and load sheet configurations as JSON
Multilingual: German and English, switchable directly in the N-panel
Adjustable font size for cutting diagram labels


Installation

Save the file as .py (e.g. cutter_x_list.py)
In Blender: Edit → Preferences → Add-ons → Install...
Select the file and enable it via the checkbox
The panel appears in the 3D viewport under N-Panel → Cutlist

Optional dependencies
Some export functions require external Python packages that must be installed into Blender's bundled Python environment:
PackagePurposeRequiredopenpyxlXLSX exportyesreportlabPDF exportoptionalPillow (PIL)Cutting diagram PNGoptional
Installation into Blender's Python (adjust path):
bash"<Blender-Path>/python/bin/python.exe" -m pip install openpyxl reportlab Pillow

Usage
1. Create sheets
In the Cutlist panel, click + to add a new sheet and fill in the fields:

Sheet name — e.g. "Birch Plywood"
Length / Width / Thickness in mm
Comment — free text
Orientation — longitudinal or crosswise (determines how parts are oriented on the sheet)

The Create sheet material button creates a Blender material with a unique name following the pattern <sheet_name>_<thickness>mm_<length>x<width>. This material can be assigned to the corresponding mesh objects — the add-on later uses it to match parts to the right sheet.
2. Prepare mesh objects
Every mesh object in the scene is interpreted as a cut part. Dimensions are derived from the bounding-box values (X/Y/Z), sorted as length ≥ width ≥ thickness. To assign a part to a specific sheet, the corresponding sheet material must be applied to the object.
3. Save and load presets
Sheet configurations can be saved under any name. JSON files are stored in the Blender user resource directory as cutlist_<preset_name>.json.
4. Export
ButtonResultExport cutlist as XLSXExcel file with sheet requirement overview and detailed parts listExport cutlist as PDFA4 landscape PDF table of all mesh partsCutting diagram (nesting)PNG with visual layout of all parts on the sheets
The XLSX export additionally lets you choose whether to export all mesh objects or only the selected ones, and whether to include objects with "sketch" in their name.

Nesting logic
The add-on calculates sheet requirements using a simple grid method:

Saw kerf is fixed at 4 mm
For each sheet, the maximum number of parts that fit in the chosen orientation (longitudinal or crosswise) is calculated
Parts are not rotated automatically — the sheet orientation determines part orientation

The nesting approach is intentionally kept simple and is not an optimizing solver. For complex mixed layouts, manual review of the cutting diagram is recommended.

Known limitations

Parts are not rotated to optimize yield — the sheet orientation applies to all parts equally
The saw blade thickness (4 mm) is hard-coded
The nesting in the PNG export places parts row by row from left to right, with no offcut optimization
comment and orientation are read from mesh objects if matching custom properties exist — by default Blender objects do not have these


License
No license specified in the file header — please contact the author before redistributing the add-on.

Locations

Panel: 3D viewport → N-panel → Cutlist
Presets: <Blender user resource>/cutlist_<name>.json

Let me know if you'd like an example workflow section, screenshots, or a changelog added.
