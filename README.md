# Tibia map data [![Build status](https://travis-ci.org/tibiamaps/tibia-map-data.svg)](https://travis-ci.org/tibiamaps/tibia-map-data)

This repository hosts (almost) fully explored [Tibia](https://secure.tibia.com/) maps in a custom format that is more suitable for version control systems than [the original, binary format](http://www.tibiamaps.org/into-the-automap-format-c-client/).

[The `tibia-maps` script](https://github.com/tibiamaps/tibia-maps-script) can be used to convert from either format to the other.

The custom format consists of three files for each floor:

1. a PNG image containing the entire map;
2. a PNG image visualizing the pathfinding data;
3. a JSON file containing the marker info, if any.

## Using the PNGs

Feel free to use the generated data in your own projects. For example, if you need Tibia maps in PNG format, you could hotlink the following URLs:

* [`https://tibiamaps.github.io/tibia-map-data/floor-00-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-00-map.png)
* [`https://tibiamaps.github.io/tibia-map-data/floor-01-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-01-map.png)
* [`https://tibiamaps.github.io/tibia-map-data/floor-02-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-02-map.png)
* [`https://tibiamaps.github.io/tibia-map-data/floor-03-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-03-map.png)
* [`https://tibiamaps.github.io/tibia-map-data/floor-04-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-04-map.png)
* [`https://tibiamaps.github.io/tibia-map-data/floor-05-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-05-map.png)
* [`https://tibiamaps.github.io/tibia-map-data/floor-06-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-06-map.png)
* [`https://tibiamaps.github.io/tibia-map-data/floor-07-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-07-map.png) (i.e. ground floor)
* [`https://tibiamaps.github.io/tibia-map-data/floor-08-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-08-map.png)
* [`https://tibiamaps.github.io/tibia-map-data/floor-09-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-09-map.png)
* [`https://tibiamaps.github.io/tibia-map-data/floor-10-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-10-map.png)
* [`https://tibiamaps.github.io/tibia-map-data/floor-11-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-11-map.png)
* [`https://tibiamaps.github.io/tibia-map-data/floor-12-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-12-map.png)
* [`https://tibiamaps.github.io/tibia-map-data/floor-13-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-13-map.png)
* [`https://tibiamaps.github.io/tibia-map-data/floor-14-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-14-map.png)
* [`https://tibiamaps.github.io/tibia-map-data/floor-15-map.png`](https://tibiamaps.github.io/tibia-map-data/floor-15-map.png)

That way, as soon as the maps are updated here, your project gets the same updates automatically.

## Contributing

Not sure where to explore? [View the open issues.](https://github.com/tibiamaps/tibia-map-data/issues?q=is%3Aissue+is%3Aopen)

The easiest and best way to contribute maps is to create a [Tibiacast](https://www.tibiacast.com/) recording of you exploring the area, walking along the edges as closely as possible. Then, [file an issue linking to your recording](https://github.com/tibiamaps/tibia-map-data/issues/new). **This method of contribution is strongly preferred.**

Alternatively, if you’re comfortable using command-line tools and Git, you could follow the instructions below to work with the map files directly. Use the official Tibia client to update your maps, [convert the maps to PNGs and JSON](#map--png--json), and submit a pull request containing your changes.

## Set up

1. Install [Node.js v4+](https://nodejs.org/en/).

2. Install the `tibia-maps` command-line utility:

    ```sh
    npm install -g tibia-maps
    ```

3. Clone this repository and `cd` to it in your favorite terminal.

## `*.map` → `*.png` + `*.json`

_If you’ve added new markers or explored new areas in-game, and you want to contribute them to our map data, then this is what you’re looking for. Copy the new map files to the `Automap` directory before continuing._

To generate PNGs for the maps + pathfinding visualization and JSON for the marker data based on the map files in the `Automap` directory, run:

```sh
tibia-maps --from-maps=./Automap --output-dir=./data
```

The output is saved in the `data` directory.

## `*.png` + `*.json` → `*.map`

_If you’ve modified marker data by editing the JSON files, and you’re looking to contribute those changes back to our map data, then this is what you’re looking for._

To generate Tibia-compatible `*.map` files based on the PNGs and JSON files in the `data` directory, run:

```sh
tibia-maps --from-data=./data --output-dir=./Automap-new
```

The output is saved in the `Automap-new` directory.

## Maintainer

| [![twitter/mathias](https://gravatar.com/avatar/24e08a9ea84deb17ae121074d0f17125?s=70)](https://twitter.com/mathias "Follow @mathias on Twitter") |
|---|
| [Mathias Bynens](https://mathiasbynens.be/) |
