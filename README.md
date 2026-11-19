# Jelly City

Washington, DC, cast in wobbling gelatin on a light table: from the Palisades, American University and Tenleytown across to Columbia Heights and Mount Pleasant, down through Cleveland Park, Adams Morgan, Shaw, Glover Park and Georgetown, across downtown and the Mall to Capitol Hill, the Navy Yard and the Southwest Waterfront, never crossing the Potomac or the Anacostia, with every building, the streets, the water, the trees and parked cars. Live at https://jellycity.walker-robinson.com.

You are a small jelly Stegosaurus. Stomp, swipe and roar; buildings wobble, squash and tear into glossy chunks, and you absorb the jelly you destroy and grow, up to five times your size. Break a landmark and cartoon missiles come for you.

- Soft bodies: every one of the 80,179 buildings is moulded from its real footprint and lidar roof (rounded, with a plinth, cornice and moulded windows). Far away they are cheap meshes that wobble on the GPU; near the dinosaur each one is cast as a smooth signed distance field mesh carried by a shape-matched lattice and skinned on the GPU, in background workers. A stomp or a hard shove tears it in rest space into uneven chunks, each recast as its own piece.
- Rendering: WebGL2. The table is a light box printed with the city map, so the jelly is lit from below; every jelly surface adds or subtracts its depth into a float target, which gives the coloured optical depth through all the jelly in front of the table. Trees and cars are instanced.

Controls: W A S D walk (relative to the camera), Shift runs, drag to look, wheel to zoom, Space stomps, a click swipes the tail, R roars. The Controls button has firmness and colorways; "Pour a new city" sets everything back up.

Made by [Walker Robinson](https://www.walker-robinson.com) with Claude.

Credits: Inspired by my aunt [Liz Hickok](https://www.lizhickok.com/)'s gelatin cities. The engine is adapted from [Stego Jelly](https://stegojelly.walker-robinson.com), which was adapted from [Whale Jelly](https://x.com/vib3coded/status/2114674922802782355) by Vib3Coded; the Stegosaurus shape is Stego Jelly's.

Data: from [Open Data DC](https://opendata.dc.gov), District of Columbia Office of the Chief Technology Officer and DDOT Urban Forestry, under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/): Building Footprints; Buildings - 3D (lidar flown 1 March 2024); Buildings (Detailed Roof); Roads 2023, Sidewalks 2023 and Waterbodies 2023 (planimetrics); DC Trees; Metro Station Entrances; Roadway Block (street centrelines, for the parked cars). For footprints with no 2024 lidar, heights come from DC's detailed-roof 3D buildings, then from OpenStreetMap (22 buildings, © OpenStreetMap contributors, [ODbL](https://www.openstreetmap.org/copyright)), then from nearby buildings of a similar size. The landmarks (the Capitol, the White House, the Washington Monument, the Lincoln and Jefferson Memorials, the Smithsonian Castle) are built by hand on their real footprints from published dimensions (Architect of the Capitol, National Park Service, White House Historical Association, Smithsonian). The map stops at DC's boundary (Open Data DC's DC Boundary layer) and at the Anacostia. The cars are generic.

Desktop only: it needs WebGL2 with float render targets (a recent desktop Chrome, Edge or Firefox). One page (`index.html`) plus the city data (`city.json`). No build step, no dependencies, no tracking. To run it locally, serve this folder with any static server, for example `python -m http.server`.
