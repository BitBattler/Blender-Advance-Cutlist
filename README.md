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
1. Download cutter_x_list.py
2. In Blender: Edit → Preferences → Add-ons → Install...
3. Select the file and enable the checkbox
4. Open the N-Panel in the 3D Viewport → "Cutlist" tab
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
1. Model your project parts as mesh objects in Blender
2. Define the sheets you have in stock (or load a preset)
3. Create materials for each sheet type
4. Assign the matching material to each part
5. Export to your preferred format and head to the shop


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
