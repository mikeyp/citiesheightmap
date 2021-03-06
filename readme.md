![Isle of Scalpay](screenshot.jpg)

# Cities: Skylines heightmap generator

A Python script to download and convert real-world elevation data for use in the Cities: Skylines map editor.

The source of the data is NASA's SRTM, which provides 90m resolution globally.

Main feature compared to https://terrain.party/ is improved handling of water and negative altitudes. This means islands and polders work out of the box.

Main downside is that it's probably more buggy and harder to use, especially if you don't live on the same side of the world as me.

## Installation

Since Cities: Skylines runs on Windows, you'll probably want to run this under Windows. For the love of god, please use Anaconda, to save yourself a week of dependency hell. Anaconda ships with many scientific libraries such as Numpy, Scipy and Matplotlib and many more are available.

```
pip install requests pyshp pypng
conda install rasterio
```

## Usage

```
usage: heightmap.py [-h] [--span SPAN] [--height-scale HEIGHT_SCALE]
                    [--blur BLUR] [--sealevel SEALEVEL] [--seabed SEABED]
                    [--fix_water] [--no-fix-water]
                    name lat lon

Generate a height map

positional arguments:
  name                  The name of the location
  lat                   Latitude
  lon                   Longitude

optional arguments:
  -h, --help            show this help message and exit
  --span SPAN           The size of the map in kilometer (default: 18)
  --height-scale HEIGHT_SCALE
                        Real height to game height. (default: 64)
  --blur BLUR           Blur radius to smooth terrain (default: 2)
  --sealevel SEALEVEL   The reference height for the map. (default: 40)
  --seabed SEABED       The relative altitude of the bottom of the sea
                        (default: -10)
  --fix_water           Replace water areas with the seabed value (default:
                        True)
  --no-fix-water

```
