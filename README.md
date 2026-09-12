# GMT 3D Grid KKT — 3D Perspective Relief Models of the Kuril-Kamchatka Trench

GMT (Generic Mapping Tools) shell scripts building three-dimensional perspective relief models of the Kuril-Kamchatka Trench region. Elevation grids are rendered as shaded 3D surface / mesh models with grdview and composited on top of a 2D geoid contour plot, viewed from controlled azimuths. The scripts have been used to generate 3D figures in the author's marine-geophysical and cartographic publications.

## What the scripts do

- clip a regional relief subset (grdcut) and build a colour palette from it (grd2cpt)
- draw a 2D geoid contour underlay in perspective (grdcontour, EGM96)
- add coastlines, ticks and a directional rose in perspective (pscoast)
- render the relief as a 3D surface / mesh with vertical exaggeration (grdview -JZ, -Qm/-Qs) at a set azimuth and elevation (-p)
- add titles, perspective-view labels and the GMT logo (pstext, logo)
- clean up temporary CPTs (rm) and export to raster (psconvert) at high resolution

Two perspective azimuths are provided (135 and 165 degrees).

## Data sources

Global relief / bathymetry: ETOPO (5 arc-minute), via GMT earth_relief tiles; geoid contours from EGM96. Coastlines from GSHHG via GMT.

## Files

- GMT-02-script-3D-grid two az135.sh: 3D model, 135-degree azimuth
- GMT-02-script-3D-grid two az165.sh: 3D model, 165-degree azimuth
- GMT-script-3D-grid.sh: base 3D-grid script

## Requirements

- GMT 6.x (Generic Mapping Tools): https://www.generic-mapping-tools.org
- A POSIX shell (bash/sh)
- The relevant relief grid (ETOPO / earth_relief) and EGM96 geoid grid available locally

## Usage

Place the required grids in the working directory, adjust the -R region, -p perspective and -JZ vertical scale at the top of the chosen script, then run:

    bash "GMT-02-script-3D-grid two az165.sh"

The script writes a PostScript file and converts it to a raster image (JPG/PNG) via psconvert.

## Author and citation

Polina Lemenkova
ORCID: https://orcid.org/0000-0002-5759-1089

These scripts support 3D figures in the author's marine-geophysical and cartographic papers; please cite the specific article a given figure appears in. The full publication list is available via the ORCID record above.

## License

See the LICENSE file in this repository.
