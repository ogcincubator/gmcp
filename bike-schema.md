# Bicycle facility

## Properties

- <a id="properties/type"></a>**`type`** *(string)*: Must be: `"FeatureCollection"`.
- <a id="properties/name"></a>**`name`** *(string)*
- <a id="properties/features"></a>**`features`** *(array)*
  - <a id="properties/features/items"></a>**Items** *(object)*
    - <a id="properties/features/items/properties/type"></a>**`type`** *(string, required)*: Must be: `"Feature"`.
    - <a id="properties/features/items/properties/properties"></a>**`properties`** *(object, required)*
      - <a id="properties/features/items/properties/properties/properties/id"></a>**`id`** *(number or string)*: A unique and stable identifier for the road segment.

        Examples:
        ```json
        "14232514"
        ```

      - <a id="properties/features/items/properties/properties/properties/Usage"></a>**`Usage`** *(string)*: Usage of the path. Restricted to one value. Must be: `"Bike Lane"`.
      - <a id="properties/features/items/properties/properties/properties/Road%20Name"></a>**`Road Name`** *(string)*: Road name.

        Examples:
        ```json
        "Pine Street"
        ```

      - <a id="properties/features/items/properties/properties/properties/BIKE"></a>**`BIKE`** *(string, required)*: Whether the segment allows bikes, and if so, what route type it is. Must be one of: "SEPARATE_TRAIL", "SHARED_ROAD", or "BIKE_LANE".

        Examples:
        ```json
        "SEPARATE_TRAIL"
        ```

      - <a id="properties/features/items/properties/properties/properties/ST_NAME"></a>**`ST_NAME`** *(string)*: Street Name and Type (the words Street, Avenue can be abbreviated).

        Examples:
        ```json
        "Stone Way N."
        ```

      - <a id="properties/features/items/properties/properties/properties/RT_NAME"></a>**`RT_NAME`** *(string or null)*: Route Name.

        Examples:
        ```json
        "Southeast 52nd Street."
        ```

      - <a id="properties/features/items/properties/properties/properties/BIKE_RT"></a>**`BIKE_RT`** *(string or null)*: Bike Route Name.

        Examples:
        ```json
        "Burke-Gilman Trail"
        ```

        ```json
        "Cheshiahud Lake Union Loop"
        ```

      - <a id="properties/features/items/properties/properties/properties/NEIGHBH"></a>**`NEIGHBH`** *(string or null)*: Neighborhood name.

        Examples:
        ```json
        "Wallingford"
        ```

      - <a id="properties/features/items/properties/properties/properties/CITY"></a>**`CITY`** *(string)*: City name.

        Examples:
        ```json
        "Seattle"
        ```

      - <a id="properties/features/items/properties/properties/properties/ADMIN"></a>**`ADMIN`** *(string)*: Highest level of administrative area.

        Examples:
        ```json
        "WA, New South Wales"
        ```

        ```json
        "County Cork"
        ```

      - <a id="properties/features/items/properties/properties/properties/POSTAL"></a>**`POSTAL`** *(string or integer)*: Zip code / postal code.

        Examples:
        ```json
        98101
        ```

      - <a id="properties/features/items/properties/properties/properties/SURFACE"></a>**`SURFACE`** *(string)*: Road Surface. Must be one of: "Paved", "Unpaved", or null.

        Examples:
        ```json
        "Paved"
        ```

      - <a id="properties/features/items/properties/properties/properties/SPEED_LM"></a>**`SPEED_LM`** *(number, string, or null)*: Speed limit in MPH or KPH.

        Examples:
        ```json
        "32 KPH"
        ```

        ```json
        "20mph"
        ```

      - <a id="properties/features/items/properties/properties/properties/CAR_RESTR"></a>**`CAR_RESTR`** *(string or null)*: Whether the segment allows cars and trucks. Must be one of: "DISALLOWED", "ALLOWED", or null.

        Examples:
        ```json
        "ALLOWED"
        ```

      - <a id="properties/features/items/properties/properties/properties/PED_RESTR"></a>**`PED_RESTR`** *(string or null)*: Whether the segment allows pedestrian use. Must be one of: "DISALLOWED", "ALLOWED", or null.

        Examples:
        ```json
        "ALLOWED"
        ```

      - <a id="properties/features/items/properties/properties/properties/DIR"></a>**`DIR`** *(string or null)*: Identifies the direction of travel. Must be one of: "BI-DIRECTIONAL", "FORWARD", "REVERSE", or null.

        Examples:
        ```json
        "FORWARD"
        ```

      - <a id="properties/features/items/properties/properties/properties/BIKESAFETY"></a>**`BIKESAFETY`** *(string)*: Are there any known safety concerns with this bicycle route. Must be one of: "RECOMMENDED", "CAUTION", "NEUTRAL", "ILLEGAL", or null.

        Examples:
        ```json
        "RECOMMENDED"
        ```

    - <a id="properties/features/items/properties/geometry"></a>**`geometry`** *(object, required)*
      - <a id="properties/features/items/properties/geometry/properties/type"></a>**`type`** *(string, required)*: Must be one of: "MultiLineString" or "LineString".
      - <a id="properties/features/items/properties/geometry/properties/coordinates"></a>**`coordinates`** *(array, required)*
        - <a id="properties/features/items/properties/geometry/properties/coordinates/items"></a>**Items** *(array)*
          - <a id="properties/features/items/properties/geometry/properties/coordinates/items/items"></a>**Items** *(array)*: Length must be at least 2.
            - <a id="properties/features/items/properties/geometry/properties/coordinates/items/items/items"></a>**Items** *(number)*
