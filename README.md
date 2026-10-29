# side_dyna_new

CAD geometry of a vehicle roll cage with a **side impact wall** built along the side of the cage.

## File

| | |
|---|---|
| File | `side_dyna_new.stp` (~4.1 MB, ~56k lines) |
| Format | STEP (ISO 10303-21), application protocol **AP214** (`AUTOMOTIVE_DESIGN`) |
| Exported with | HOOPS Exchange 2025.2 (v25.2.0) |
| Author / date | aadit, 2026-07-08 |
| Units | millimetres, angles in degrees |
| Tolerance | 1e-3 mm (assembly), 1e-5 mm (part geometry) |

## Contents

The file is a small assembly of three parts:

- **`Geom`** (two instances): the roll cage tube members.
- **`Midsurface - Solid`**: a single midsurface sheet (`Midsurface1`). This is the side impact wall.

### Roll cage tubes

- 56 surface bodies (`SHELL_BASED_SURFACE_MODEL` / `OPEN_SHELL`). There are no closed solids.
- The tubes are made of cylindrical faces (straight runs) and toroidal faces (bends): 140 cylinders and 44 tori.
- There are two tube sizes:
  - radius 13.775 mm, so outer diameter **27.55 mm** (76 faces)
  - radius 12.2 mm, so outer diameter **24.4 mm** (64 faces)
- 12 different RGB colours are used to tell the members apart.

### Side impact wall

- A single curved face (cylindrical surface, R = 102 mm) on the side of the cage at about X = −493 mm.
- It covers about 1,270 mm along Y (−13 to 1,259 mm) and sits about Z = 522–624 mm.
- It is stored as a midsurface with no thickness. Set its shell thickness in the pre-processor.

### Overall extents (approx., mm)

| Axis | Min | Max |
|---|---|---|
| X | −1,307 | 539 |
| Y | −28 | 1,408 |
| Z | −470 | 624 |

## Usage notes

- All the geometry is surfaces (tube outer skins plus one midsurface), so it can be meshed directly with shell elements. The file name suggests it is set up for an LS-DYNA side impact analysis.
- The file opens in any STEP-capable CAD/CAE tool (SolidWorks, CATIA, NX, Fusion 360, FreeCAD, ANSA, HyperMesh, LS-PrePost).
- Tube wall thickness and material are not stored in the file. Define them as section properties when you set up the analysis.
