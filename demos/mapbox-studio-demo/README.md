## Mapbox Studio Demo

For more detailed examples and tutorials, look at the [Source Quickstart](https://www.mapbox.com/mapbox-studio/source-quickstart/) and [Style Quickstart](https://www.mapbox.com/mapbox-studio/style-quickstart/) for Mapbox Studio.

[Mapbox Studio can be downloaded here](https://www.mapbox.com/mapbox-studio)

### Create vector tiles:
1. Open Mapbox Studio
2. Create a new blank source project
3. 'Create Layer' and add your graticule data
4. Save your source project.
5. Open the 'Settings' pane, update the project metadata, and upload it to Mapbox.com.

### Style your vector tiles
To composite your graticule data onto an existing map style in Mapbox Studio, follow all of the instructions.

To create a translucent graticule base layer that you can overlay on other maps in the browser with a javascript mapping library, select "Create style from source" from the source view of Mapbox Studio and skip to step 8.

1. Create a new project and select a style template you like.
2. Select the 'Layers' pane and 'Change Source.'
3. You should see a list of the source data available to you. If your source data is remote, you can overlay several remote sources on top of one another. Find your graticules layer and copy the mapid.
4. Paste the mapid after `mapbox.mapbox-streets-v5`. Make sure there is only a comma in between your graticules' mapid and `mapbox.mapbox-streets-5` -- no spaces allowed. Which ever mapid is last will be availabe on the top of the map (LIFO). Click 'Apply'.
5. In your layers pane, you will see `#ne_10m_graticules_30` on the top of the layers list.
6. Create a new stylesheet by clicking on the '+' in the top right corner of Mapbox Studio. Name it `graticule`.
7. Add this to your new stylesheet and save your project:
    ```
    #ne_10m_graticules_10 {
        line-width: 2;
        line-color: blue;
    }
    ```

8. You can style your graticule lines any way you like. You can even make selections on the data by adding `[{data_layer_field_key}{comparison operator}(data_layer_field_value}]` e.g.
    ```
    #ne_10m_graticules_10[direction='N'] {
      line-width: 2;
      line-color: blue;
    }
    ```

9. Save your project and upload it to Mapbox.com

Now you have a style with a mapid that you can use with [Mapbox.js](http://www.mapbox.com/mapbox.js) and put your map into a website or application!