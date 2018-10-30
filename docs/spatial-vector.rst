Earthpy Spatial Vector Data
===========================

The ``earthpy`` spatial vector module provides functions that wrap around ``geopandas`` to work with vector data in Python.

Both layers must be the same Coordinate Reference System (CRS).

Clip Points
-----------

The ``clip_point`` function takes a shapefile to clip to another shapefile. 

``clip_point`` takes 2 input parameters:

``shp``: **geopandas dataframe**
    Vector layer (point, line, polygon) to be clipped to clip_obj.

``clip_obj``: **geopandas dataframe**
    Dataset to be clipped.
    
The ``clip_point`` function returns the following:

Points clipped to vector boundary.

Example:

.. code-block:: python

  import geopandas as gpd
  import clip_data as cl

  # Import shapefile using geopandas
  point_path = gpd.read_file("point_path_filename.shp")

  # Import clip object using geopandas
  boundary_path = gpd.read_file("boundary_path_filename.shp")
  
  point_clip = cl.clip_shp(point_path, boundary_path)
