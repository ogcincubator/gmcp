# README

Exploring validation tools for geospatial features stored in [GeoJSON](https://www.rfc-editor.org/rfc/rfc7946.html) and [JSON-FG](https://github.com/opengeospatial/ogc-feat-geo-json?tab=readme-ov-file). 🛠

## Dataset 🗂

The [sample GeoJSON dataset](bike_lane.geojson) was created from an example on the [GMCP page](https://support.google.com/mapcontentpartners/answer/144284#zippy=%2Cbicycle-facilities); it represents bike lanes.

![bike lane](bike-lane.png)

There are several variations of the dataset, to check with the validator:
* `bike_lane.geojson`: valid in every aspect;
* `bike_lane_fail_RFC.geojson`: invalid GeoJSON structure;
* `bike_lane_fail_schema.geojson`: invalid JSON Schema;
* `bike_lane fail_geom.geojson`: invalid geometry;

The [sample schema](bike-schema.json) was created based on the information on section "Bicycle facility fields/attributes" of the same page; it uses [JSON Schema draft-07](https://json-schema.org/).

The [sample JSON-FG dataset](bike_lane.jsonfg) was created from the GeoJSON, using GDAL:

```
 ogr2ogr -f "JSONFG" bike_lane.jsonfg bike_lane.geojson
```

This file was then modified to match the latest version of the Standard and to add a Feature Schema.

## GeoJSON

We try to answer these questions about the GeoJSON file:
* *Is it a valid GeoJSON file?*
* *Does it contain valid geometry?*
* *Are the attributes according to what we expect?*

### Validation ✅

This repository shows validation of a GeoJSON dataset, using three approaches:
1. *Format Structure validation using GeoJSON*: checks if format is valid, according to RFC 7946.
2. *Geometry validation using GDAL*: checks if geometry exists and is valid.
3. *JSON Schema validation*: validates against a provided JSON schema file, which also defines how the attributes should look like.

Level 3 is the most complete and most strict type of validation.

You can also validate the geometry and the schema using online tools:
* https://geojsonlint.com/
* https://www.itb.ec.europa.eu/json/geojson/upload
* https://www.jsonschemavalidator.net/
* https://jsonschema.dev/

### Run validation 🎬

Start the notebook with:

```
jupyter notebook
```

Run the different validators on [geojson-validation.ipynb](geojson-validation.ipynb).

## JSON-FG

Features and Geometries JSON is a (candidate) Standard from OGC. It extends GeoJSON to add additional (minimal) capabilities which are important for the geospatial community; these include:
* Ability to use CRS other than WGS84
* Support for 3D types and complex geometries
* Ability to encode temporal characteristics of a feature
* Declare feature types, supported by schemas

It is a "richer" format than GeoJSON, maintaining (if necessary) the backwards compatibility.

### Validation ✅

Since this a newer (although already widely supported) Standard, there are less tools available for validation. To check the structure of the file against the Standard, one can use the [ogc checker](https://github.com/geonovum/ogc-checker), which runs a hosted version [here](https://geonovum.github.io/ogc-checker/#/json-fg); a CLI is being added to this tool, which will enable integration into a validation pipeline, for instance through a GitHub action.

However, we are yet to see validators that leverage the full power of the format. Since the reference to the schema is embedded within the file, a JSON-FG validator can use JSON schema directly, to assess if the features are correct.

In the notebook provided, we run two validation approaches on this file:

1. *Geometry validation using GDAL*: checks if geometry exists and is valid.
2. *JSON Schema validation*: validates against a provided JSON schema file, which also defines how the attributes should look like.

Start the notebook with:

```
jupyter notebook
```

Run the different validators on [jsonfg-validation.ipynb](jsonfg-validation.ipynb).

## License

This project is released under an [MIT License](./LICENSE)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
(dev-exercise-template)