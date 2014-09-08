# Atlastory Roadmap

![](./_img/Atlastory-Stack.png?raw=true)

| Purpose             | Codebase      | Description                        | Phase I                                          | Phase II                   |
|---------------------|---------------|------------------------------------|--------------------------------------------------|----------------------------|
| ***Store & access data*** | [api](https://github.com/atlastory/api)          | Map data storage, acces, importing | api.atlastory.com, Github                        | api.atlastory.com          |
| ***Edit data***           | Editor.js     | Client-side map editing library    | Desktop GIS applications                         | edit.atlastory.com         |
| ***Render maps***         | tile-renderer | Tile rendering / storage           | TileMill                                         | Atlastory render server(s) |
| ***Access maps***         | tile-server   | Tile serving                       | MapBox                                           | tiles.atlastory.com        |
| ***View maps***           | [Atlastory.js](https://github.com/atlastory/Atlastory.js)  | Client-side map viewing library    | map.atlastory.com                                | atlastory.com              |
| ***Collaboration***       | forum         | Discussion boards                  | [Atlastory Mappers](http://forum.atlastory.com/) (Google Groups), Github issues | (?)                        |
| ***Documentation***       | wiki          | Wiki documentation                 | Github                                           |                            |

### Current status: Phase I

* **Store & access data**: Maps are being transferred from the [Github base-map repo](https://github.com/atlastory/base-map) to the API. The API is in working condition with the ability to store map data, edit data through changesets, import GeoJSONs, access data through a RESTful interface, and export GeoJSON (though very slowly for now).
* **Edit data**: Using any GIS editing application that can export to GeoJSON.
* **Render maps**: Using TileMill, a desktop mapmaking app from MapBox, to style and render map tiles from API-exported GeoJSONs.
* **Access maps**: Using a paid MapBox account to store and serve tile images.
* **View maps**: The version 1 of Atlastory.js uses Leaflet and other custom code to display demo maps on a timeline at *map.atlastory.com*.
* **Collaboration**8: A combination of Google Groups (for mapping) Github issues (for development).
* **Documentation**: Using markdown files on Github + API documentation.

### Roadmap to Phase II

1. **API** — The API and database are fully functional, managing all map data and associated changesets for users, with full documentation and fast response times (see the more detailed [api/TODO](https://github.com/atlastory/api/blob/master/TODO.md)).
2. **Editor.js** — A finished client-side javascript library that connects to the API, manages all data, creates a vector-based map with GIS-like editing capabilities, allows editing and submission of changesets. Everything needed to edit Atlastory maps on your browser except the UI itself (with some default map styling & components). This will be attached to a UI at *edit.atlastory.com* or on any other contributing editor.
3. **Tile-renderer** — A single-use application that (1) takes inputs of map area, layers, and period to retrieve raw map data from the database; (2) renders it into vector-tiles; and (3) stores the tiles on a static server.
4. **Tile-server** — A server allowing users to request via URL map tiles in any format (vector, PNG, JPG). It takes both raw vector tiles from a static server and a map stylesheet and renders them realtime using Mapnik into finished tiles.


