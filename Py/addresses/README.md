## Create a Panda Data Frame with Geocode Ready Address Data 

The python scripts creates a Panda data frame that can be imported and persisted into the Insights workbook for further analysis.

__Steps__

1) In the first cell paste this code and then click Run (or _Shift-Enter_)

    ```python
    import pandas as pd
    import numpy as np

    df = pd.DataFrame(np.array([
    ["1001 19th St North", "Arlington", "VA", "Esri R&D"],
    ["380 New York St", "Redlands", "CA", "Esri Headquarters"],
    ["920 SW #rd Avenue", "Portland", "OR", "Esri R&D"],
    ["75 Broad St", "New York City", "NY", "Esri Regional Office"]
    ]), columns=["Address", "City", "State", "Office"])
                  
    df
    ```

2) In second cell paste this code (or use the magic command _Ctrl-Alt-B_ passing in ```df```) and run.  Notice the layer named ```Layer``` that gets created in the _Data Pane_

    ```python
    %insights_return(df)
    ```

3) Next click the ellipse next to ```Layer``` in the _Data Pane_ and select __Enable Location__.  Choose _Address_ and _Esri World Geocoder_.  Then click Run.


4) Notice a new field _Location_ within the layer.  This is geometry field containing spatial data.  Next drag layer onto the canvas to create a Map (by dropping the layer in the _drop zone_ named _Map_).