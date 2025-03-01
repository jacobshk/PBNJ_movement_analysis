### given: video 
### assume: 
- video is top down view of scene containing animal 
- background scene will not change; camera position/angle is static
- animal will traverse scene over time
- animal will contain some tether, should be ignored
- animal will be marked (per discuss w/diego); red dot on head
* background will be other color, distinct from head (e.g. white) 
- only one animal per scene (TODO: multi obj taggign via centroids?)



### requirements: program should
- extract animal location at every frame (background sub, ignore tether/center of mass?)
- extract animal head direction at every frame (assume mouse; relative to center of mass, where is red dot?)


- user should be able to:
* create zone overlay (pie chart style? grid? polygons?) => per frame, log zone animal is in

* create goal zones (i.e. polygons) => per frame, log animal distance from zone 

- program should output:
* heatmap of animal location over time (like this: https://www.maptive.com/wp-content/uploads/2020/10/us_library_heat_map-1.png)

* video_log CSV containing columns:
    1. frame number (0 => N; CSV will have N rows) 
    2. timestamp
    3. animal x coord
    4. animal y coord
    5. animal direction (in terms of degrees, assuming bottom line is 0)
    6. animal distance from each zone (i.e. to deduce which zone animal is in, regardless of overlap)
    7. animal distance from each goal zone 

* video_config CSV containing columns
    1. each zone's polygons 
    2. goal zone polygons