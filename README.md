🪚 Cutter-x-list

A Blender add-on for woodworkers, makers, and fabricators — turn your 3D models into ready-to-use cut lists, sheet requirement overviews, and visual cutting diagrams in seconds.

<p align="center">
  <img src="https://img.shields.io/badge/Blender-4.5%2B-orange?logo=blender&logoColor=white" alt="Blender 4.5+">
  <img src="https://img.shields.io/badge/Python-3.11-blue?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/version-1.0-green" alt="Version 1.0">
  <img src="https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey" alt="Platform">
  <img src="https://img.shields.io/badge/language-EN%20%7C%20DE-yellow" alt="Languages">
</p>

✨ What it does
Cutter-x-list reads the mesh objects in your Blender scene and generates everything you need to take your design from screen to workshop:
📊 Excel cut lists with grouped quantities and sheet requirement summaries
📄 PDF tables ready to print and bring to the shop
🖼️ Visual nesting diagrams showing how parts fit on each sheet
💾 Reusable presets for your standard sheet stock
🌍 Bilingual UI — English and German, switchable on the fly

🚀 Quick Start
bash# 1. Download cutter_x_list.py
# 2. In Blender: Edit → Preferences → Add-ons → Install...
# 3. Select the file and enable the checkbox
# 4. Open the N-Panel in the 3D Viewport → "Cutlist" tab
That's it. You're ready to cut. 🎉

📦 Dependencies
Some export features rely on external Python packages installed inside Blender's bundled Python:
PackagePurposeRequiredopenpyxlXLSX export✅reportlabPDF export⚪PillowCutting diagram (PNG)⚪
<details>
<summary><b>📥 How to install dependencies</b></summary>
Open a terminal and run (adjust the path to your Blender installation):
bash"<Blender-Path>/python/bin/python.exe" -m pip install openpyxl reportlab Pillow
Example paths:

Windows: "C:\Program Files\Blender Foundation\Blender 4.5\4.5\python\bin\python.exe"
macOS: /Applications/Blender.app/Contents/Resources/4.5/python/bin/python3.11
Linux: /usr/share/blender/4.5/python/bin/python3.11

</details>

🛠️ Features in Detail
🟫 Sheet Management
Define any number of sheet types — each with name, dimensions, thickness, comment, and grain orientation. Add new sheets, remove old ones, and edit details right in the side panel.
🎨 Material Generation
One click creates a Blender material per sheet, named:
<sheet_name>_<thickness>mm_<length>x<width>
Assign it to your mesh parts, and the add-on automatically maps them to the right sheet during export.
📊 XLSX Export
Generates a structured spreadsheet containing:

📋 Sheet requirements — how many sheets of each type you need
🧾 Detailed parts list — grouped by dimensions, with quantities, materials, comments, and orientation
⚙️ Filter options — export all meshes or selection only, include/exclude sketch objects

📄 PDF Export
A clean, printable A4 landscape table of all parts in your scene. Perfect for the workshop wall.
🖼️ Nesting Diagram
Renders a visual PNG showing how parts are placed on each sheet — with labels, dimensions, and orientation indicators. Adjust font size to taste.
💾 Presets
Save your common sheet configurations as JSON files and reload them across projects. Stored in your Blender user resource directory.
🌐 Multilingual
Switch between 🇬🇧 English and 🇩🇪 German directly in the panel header.

🪵 Workflow
#mermaid-r3k5{font-family:inherit;font-size:16px;fill:#E5E5E5;}@keyframes edge-animation-frame{from{stroke-dashoffset:0;}}@keyframes dash{to{stroke-dashoffset:0;}}#mermaid-r3k5 .edge-animation-slow{stroke-dasharray:9,5!important;stroke-dashoffset:900;animation:dash 50s linear infinite;stroke-linecap:round;}#mermaid-r3k5 .edge-animation-fast{stroke-dasharray:9,5!important;stroke-dashoffset:900;animation:dash 20s linear infinite;stroke-linecap:round;}#mermaid-r3k5 .error-icon{fill:#CC785C;}#mermaid-r3k5 .error-text{fill:#3387a3;stroke:#3387a3;}#mermaid-r3k5 .edge-thickness-normal{stroke-width:1px;}#mermaid-r3k5 .edge-thickness-thick{stroke-width:3.5px;}#mermaid-r3k5 .edge-pattern-solid{stroke-dasharray:0;}#mermaid-r3k5 .edge-thickness-invisible{stroke-width:0;fill:none;}#mermaid-r3k5 .edge-pattern-dashed{stroke-dasharray:3;}#mermaid-r3k5 .edge-pattern-dotted{stroke-dasharray:2;}#mermaid-r3k5 .marker{fill:#A1A1A1;stroke:#A1A1A1;}#mermaid-r3k5 .marker.cross{stroke:#A1A1A1;}#mermaid-r3k5 svg{font-family:inherit;font-size:16px;}#mermaid-r3k5 p{margin:0;}#mermaid-r3k5 .label{font-family:inherit;color:#E5E5E5;}#mermaid-r3k5 .cluster-label text{fill:#3387a3;}#mermaid-r3k5 .cluster-label span{color:#3387a3;}#mermaid-r3k5 .cluster-label span p{background-color:transparent;}#mermaid-r3k5 .label text,#mermaid-r3k5 span{fill:#E5E5E5;color:#E5E5E5;}#mermaid-r3k5 .node rect,#mermaid-r3k5 .node circle,#mermaid-r3k5 .node ellipse,#mermaid-r3k5 .node polygon,#mermaid-r3k5 .node path{fill:transparent;stroke:#A1A1A1;stroke-width:1px;}#mermaid-r3k5 .rough-node .label text,#mermaid-r3k5 .node .label text,#mermaid-r3k5 .image-shape .label,#mermaid-r3k5 .icon-shape .label{text-anchor:middle;}#mermaid-r3k5 .node .katex path{fill:#000;stroke:#000;stroke-width:1px;}#mermaid-r3k5 .rough-node .label,#mermaid-r3k5 .node .label,#mermaid-r3k5 .image-shape .label,#mermaid-r3k5 .icon-shape .label{text-align:center;}#mermaid-r3k5 .node.clickable{cursor:pointer;}#mermaid-r3k5 .root .anchor path{fill:#A1A1A1!important;stroke-width:0;stroke:#A1A1A1;}#mermaid-r3k5 .arrowheadPath{fill:#0b0b0b;}#mermaid-r3k5 .edgePath .path{stroke:#A1A1A1;stroke-width:2.0px;}#mermaid-r3k5 .flowchart-link{stroke:#A1A1A1;fill:none;}#mermaid-r3k5 .edgeLabel{background-color:transparent;text-align:center;}#mermaid-r3k5 .edgeLabel p{background-color:transparent;}#mermaid-r3k5 .edgeLabel rect{opacity:0.5;background-color:transparent;fill:transparent;}#mermaid-r3k5 .labelBkg{background-color:rgba(0, 0, 0, 0.5);}#mermaid-r3k5 .cluster rect{fill:#CC785C;stroke:hsl(15, 12.3364485981%, 48.0392156863%);stroke-width:1px;}#mermaid-r3k5 .cluster text{fill:#3387a3;}#mermaid-r3k5 .cluster span{color:#3387a3;}#mermaid-r3k5 div.mermaidTooltip{position:absolute;text-align:center;max-width:200px;padding:2px;font-family:inherit;font-size:12px;background:#CC785C;border:1px solid hsl(15, 12.3364485981%, 48.0392156863%);border-radius:2px;pointer-events:none;z-index:100;}#mermaid-r3k5 .flowchartTitleText{text-anchor:middle;font-size:18px;fill:#E5E5E5;}#mermaid-r3k5 rect.text{fill:none;stroke-width:0;}#mermaid-r3k5 .icon-shape,#mermaid-r3k5 .image-shape{background-color:transparent;text-align:center;}#mermaid-r3k5 .icon-shape p,#mermaid-r3k5 .image-shape p{background-color:transparent;padding:2px;}#mermaid-r3k5 .icon-shape rect,#mermaid-r3k5 .image-shape rect{opacity:0.5;background-color:transparent;fill:transparent;}#mermaid-r3k5 .label-icon{display:inline-block;height:1em;overflow:visible;vertical-align:-0.125em;}#mermaid-r3k5 .node .label-icon path{fill:currentColor;stroke:revert;stroke-width:revert;}#mermaid-r3k5 :root{--mermaid-font-family:inherit;}Model partsin BlenderDefine sheetsin Cutlist panelGenerate sheetmaterialsAssign materialsto mesh partsExport📊 XLSX📄 PDF🖼️ PNG diagram

Model your project parts as mesh objects in Blender
Define the sheets you have in stock (or load a preset)
Create materials for each sheet type
Assign the matching material to each part
Export to your preferred format and head to the shop


⚙️ How Nesting Works
The add-on uses a straightforward grid-based approach:

🪚 Saw kerf is fixed at 4 mm per cut
📐 Parts fit into the sheet based on the chosen orientation (longitudinal or crosswise)
🚫 Parts are not auto-rotated to maximize yield — the sheet orientation applies uniformly


💡 Note: This is intentionally a simple algorithm, not an optimizing solver. For complex mixed layouts, review the visual cutting diagram before sending to production.


⚠️ Known Limitations

Parts are not rotated individually for optimal yield
Saw blade thickness (4 mm) is hard-coded
Nesting places parts left-to-right, row-by-row, without offcut reuse
comment and orientation are read from mesh custom properties if present — Blender objects don't have these by default


📍 File Locations
WhatWhereUI Panel3D Viewport → N-Panel → CutlistPresets<Blender user resource>/cutlist_<name>.json

🧑‍💻 Contributing
Pull requests, bug reports, and feature suggestions are welcome! Some ideas for future improvements:

 Configurable saw kerf
 Smart part rotation for better yield
 Offcut tracking and reuse
 More export formats (CSV, JSON)
 Custom properties UI for comments and orientation per object


📜 License
No license specified in the source header. Please contact the author before redistribution.

👤 Author
Tom StarSky
If this add-on saved you time in the workshop, consider giving it a ⭐ on GitHub!

<p align="center">
  Made with 🪚 and 🐍 for woodworkers who model in Blender.
</p>

A few notes on what I added: badges at the top, collapsible dependency-install section, a Mermaid workflow diagram (renders natively on GitHub), emoji section headers for scannability, a contributing checklist, and a centered footer. If you'd like, I can also generate a LICENSE file suggestion (MIT is most common for Blender add-ons), draft a CHANGELOG.md, or create placeholder spots for screenshots/GIFs once you have them.
