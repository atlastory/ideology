# Atlastory Ideology

<a name="what" />
## What

**Our objective is to create an interactive map that chronicles the history of life on earth.**

![](./_img/screencast-example.gif?raw=true)

<a name="why" />
## Why

**Our purpose is to improve understanding of the past by organizing and visualizing historic knowledge.** We believe that understanding history helps make for a better future and that the methods of presenting and distributing it are important. 

*Why an interactive map?* Maps are one of the best ways to clearly show an enormous amount of information in a small area. Adding interactivity further improves this density-to-clarity ratio. Since everything in the past took place at a certain time and location, maps are an obvious choice to visualize that knowledge. Understanding history requires seeing changes and interactions over time, and a four-dimensional map allows this.

*Why Atlastory in particular?* There are a handful of other projects working toward a similar goal or on similar technology. So why is [this](#how) the right approach?

* Given the enormity of the data collection task, content **needs to be crowdsourced**, along with major pieces of the technology stack open-sourced (like the API). Historic map data has been collected for many years by organizations around the world. Keeping this and any new data **open** increases its *accuracy*, *speed of collection* and *availability* to everyone.
* **A single entity should guide the direction of the community**, similar to the OpenStreetMap Foundation (especially regarding operations and design of the experience). Many historic mapping organizations can work in parallel collecting data from the ground up — but effectively storing, accessing, and distributing the data is best led top-down.
* **Map creation should be top down**, from global to local. The purpose of an Atlastory map is not navigation, it is understanding of history. So high map detail (minor roads, structures, etc.) is not as necessary at first. Creating a global “structure” over time will also provide context and make it easier to interest other users/contributors.
* **Infrastructure is unique and must be created from scratch.** The technological requirements to implement Atlastory are unique enough that it shouldn't built on top of other platforms (like OSM). Of course, this doesn’t include borrowing concepts and using other open-source libraries. Starting from scratch also allows the opportunity for innovation in data storage, retrieval, rendering and display.

**[>> Guiding Principles](Principles.md)**

<a name="how" />
## How

![](./_img/Atlastory-Stack.png?raw=true)

1. Build GIS storage system with API access
	* Database & structure
	* RESTful API
	* System for adding/managing multiple changesets of data
	* User accounts + API token access
2. Build historic mapping community
	* (?) Build community how-to wiki
	* Seed map content from global > local
3. Build crowdsourced historic map editor (a web-based editor that connects to the API) with the ability to:
	* Add/edit data on a local scale (basic functionality of iD from MapBox)
	* Add/edit data on a global scale (GIS functionality tailored for specific uses like drawing borders)
	* More advanced shape editing tools like split, merge, trim
    * Easily collect existing data produced by other organizations in any format
	* View modern & historic map overlays as a source (including warp tools to match projections)
	* Methods to easily find and reference archival maps
4. Build server-side tile renderer (image and vector), including:
	* Map design & styling for all zoom levels
	* Queueing app that controls the rendering process
	* Render server
	* Tile storage / serving
5. Build map viewer (client-side viewer + timeline)

See the more detailed Roadmap for exactly what has and needs to be done:

**[>> Detailed Roadmap](Roadmap.md)**

<a name="map" />
#### The Map

The design of the base map will be an elegant combination between 3 map types:

1. **Physical**, with basic landscape features and geography;
2. **Political**, with sovereign and administrative boundaries; and
3. **Cultural**, a world without boundaries, of the history of the earth and our relation to it. Culture = territory of people with common language, belief systems, norms.
4. (Major roads and infrastructure may be added in the future.)

After the base map with sufficient history has been created, the stack should be updated to allow separate “overlay” maps (historic events, statistical data, thematic maps, etc.). These maps would be blended with either the full base map or just a minimal physical map, depending on what the data and design call for.

The map levels will be layered like this:

```
——— Political
    (*) settlement: city, capital-[1-3], town, village
    ——— admin-1: sovereignty, country, dependency, colony
    ‑‑‑ admin-2: province, republic, oblast, state
    --- admin-3: county
    ∹∹∹ admin-4: city
∿∿∿ Cultural || Overlay
^=~ Physical
    ≈≈≈ lakes
    ~~~ rivers
    ^^^ terrain
    === land
```

**[>> Base Map repo](https://github.com/atlastory/base-map)**

#### Design principles

**[>> Beliefs & Models](Beliefs.md)**