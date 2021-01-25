# Name of the project (MiMap)

<!-- ABOUT THE PROJECT -->
## About The Project

[![Product Name Screen Shot][product-screenshot]](https://example.com)

There are many great README templates available on GitHub, however, I didn't find one that really suit my needs so I created this enhanced one. I want to create a README template so amazing that it'll be the last one you ever need -- I think this is it.

Here's why:
* Your time should be focused on creating something amazing. A project that solves a problem and helps others
* You shouldn't be doing the same tasks over and over like creating a README from scratch
* You should element DRY principles to the rest of your life :smile:

Of course, no one template will serve all projects since your needs may be different. So I'll be adding more in the near future. You may also suggest changes by forking this repo and creating a pull request or opening an issue. Thanks to all the people have have contributed to expanding this template!

A list of commonly used resources that I find helpful are listed in the acknowledgements.

## Features

- Main features
    - Sub features 

## Installation


### Installation

1. Get a free API Key at [https://example.com](https://example.com)
2. Clone the repo
   ```sh
   git clone https://github.com/your_username_/Project-Name.git
   ```
3. Install NPM packages
   ```sh
   npm install
   ```
4. Enter your API in `config.js`
   ```JS
   const API_KEY = 'ENTER YOUR API';
   ```

### Install fast-map-matching (optional)

The map matching implementation is relied on a thrid-party implementation [[fmm]](https://github.com/cyang-kth/fmm). I only tested this through in Linux (Ubuntu) system. I did have difficulty installing this in the Windows system. The installment of fmm will only influence the map matching module; the map data loading/processing/output is not relied on this package. The installment documentaiton can be found at: [[fmm-wiki]](https://fmm-wiki.github.io/). There are two additional things need more consideration: 

1. Remove the Python 2.7 REQUIRED in the cmakelist file located at [```fmm/python/CMakeLists.txt```](https://github.com/cyang-kth/fmm/blob/master/python/CMakeLists.txt). Just delete the ```2.7``` in line 10 and line 11.
2. Change the cmake prefix, in my Linux system and conda environment, I use:
```
cmake .. -DCMAKE_INSTALL_PREFIX=/home/xingminw/Anaconda3/envs/fmm
```

### Loading and visualization

1. Map data loading: function [```map_process.build_network_from_xml()```](mimap/map_process.py).
2. Output ```.json``` file for [leaflet visualization](#leaflet-visualization-tool): [```map_visualize.output_static_geometry_json()```](mimap/map_visualize.py)

## Leaflet visualization tool
We also developed a visualization tool 
based on [Leaflet](https://leafletjs.com/); see demo [[here]](https://xingminw.github.io/ctm-signal-opt/map.html). Here is the screenshot of the leaflet visualization tool:

![Leaflet Visualization took](docs/_static/visualization.png)

### To be developed
- [ ] Some other autofix functions
    - [ ] Auto-merge some segments that has exactly the same tags
    - [ ] Logging system for the map data error and not-for-sure inference
- [ ] **Split the map processing into two different modes: w/o autofix**
- [ ] Application based on map data: trajectory data map matching
- [ ] Test more map data to cover more corner cases (maintainence)
- [ ] Shortest path between two nodes, some other essential functions about network algorithms ([NetworkX](https://networkx.org/))
- [ ] Documentation auto-generation using SPhinx
- [ ] Current version is all about static map geometry and topology, need to define some additional attributes from the traffic parameters (OD, link/path flow, volumes) and trajectories, traffic signal timing plan, etc.)
- [ ] ~~Transportation network modeling (OD flow to the path/link flow)~~
