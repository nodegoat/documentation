## Visualisation Settings
Click the gear icon positioned to the right of the visualisation buttons to open the visualisation settings.

Define 'Scope', 'Frame', 'Context', and/or 'Visuals' settings to change the behaviour of the visualisations. Each set of settings can be stored by using the blue 'save' button. Click the green 'open' button to open a previously stored setting.

### Scope
The scope is a one-on-one representation of your data model. Use the scope to limit the data to be visualised or expand the data to be visualised. Without specifying a Scope, the currently active object or objects found by a filter are visualised. All Sub-Objects, relational Object Descriptions and relational Sub-Object Descriptions will be visualised.

To **limit** the data included in the visualisation, select the Sub-Objects, relational Object Descriptions, and relational Sub-Objects Descriptions that you want to include. All unselected Sub-Objects, relational Object Description, and relational Sub-Objects Descriptions will not be included in the visualisation. To only include the Object without any additonal elements, check the 'Object Only' checkbox.

To **expand** the data included in the visualisation, use the available relations to related Types, Classifications, and Reversed Classifications. The **🢓** icon depicts an outgoing relationship, the **🢑** icon depicts an incoming relationship. After checking a checkbox, the available Sub-Objects, relational Object Description, relational Sub-Objects Descriptions, and incoming and outgoing relations to other Types, Classifications, and Reversed Classifications will be shown. All these settings can be used in the same way as the settings of the Type, Classification, or Reversed Classification with which you started.

The Scope communicates with the **filter** functionality. You can activate path-aware filtering on referenced Types, Classifications, and Reversed Classifications by checking the 'filter' checkbox. With this configuration the set filter will be performed within the path created by the Scope.

To use the related Types, Classifications, and Reversed Classifications as a link between two or more related Types, Classifications, or Reversed Classifications, check the 'Collapse' checkbox. The collapsed elements will now be shown as links instead of nodes.

### Frame
Specify greographical and temporal boundaries and handle missing or incomplete Sub-Objects.

#### Geographical
To specify a default area for the geographical visualisation: fill in latitude and longitude values, or use the green 'map' button to select a location on the map. Set a default zoom level by specifying the scale of the geographical visualisation.

#### Social
-

#### Time
Limit the date slider by entering a boundary using the start date and end date input fields. Specify a default date selection by using the start date and end date input fields.

#### Missing or Incomplete Sub-Objects
Specify how a missing date should be handled by selecting 'Ignore', 'Span Selection', 'Prefix Selection', or 'Affix Selection'. Specify how a missing location should be handled by selecting 'Ignore', or 'Equator'.

### Context
-

### Visuals
Use these settings to customise the design and behaviour of the visualisation.

#### Geographical

##### Design

| Name  | Default value | Description |
| -- | -- | -- |
| Dot Colour | none | Colour of nodes. Overrides all other colour settings. |
| Dot Colour Condition | none | Name of the Condition that sets the colour of the node. |
| Dot Min Size | 8 | Minimal size of nodes. |
| Dot Max Size | 20 | Maximum size of nodes. |
| Dot Stroke Colour | #f0f0f0 | Colour of stroke of nodes. |
| Dot Stroke Width | 1.5 | Width of stroke of nodes. |
| Show Location | No | Display the name of a Location Reference. |
| Location Colour | #000000 | Colour of the name of a Location Reference. |
| Location Size | 8 | Size of the name of a Location Reference. |
| Location Condition | none | Name of the Condition that displays the name of a Location Reference. |
| Line Colour | none | Colour of lines. |
| Line Min Width | 2 | Minimal width of lines. |
| Line Max Width | 10 | Maximum width of lines. |
| Line Offset | 6 | Curve. |
| Show Visual Hints | Yes | Display visual hints if a new Sub-Object is shown. |
| Visual Hint Colour | #0092d9 | Colour of the visual hint. |
| Visual Hint Size | 20 | Size of the visual hint. |
| Visual Hint Stroke Colour | #ffffff | Stroke colour of the visual hint. |
| Visual Hint Stroke Width | 2 | Stroke width of the visual hint. |
| Visual Hint Duration | 0.5 | Duration of the visual hint, in seconds. |
| Visual Hint Delay | 0 | Delay of the visual hint, in seconds. |
| Show Surface | No | Display a convex hull around all nodes. |
| Surface Colour | #000000 | Colour of the convex hull. |
| Surface Opacity | 0.1 | Opacity of the convex hull. |

##### Settings

| Name | Default value | Description |
| -- | -- | -- |
| Show Geometric Information | No | Display information on the total distance, longest distance, shortest distance, and total surface. |
| Map | _Click 'Default Visuals' to load the default map tiles._ | Tile server used for the map, plus attribution information. |
| Background Colour | none | Backgound colour of the visualisation. This overrides the map tiles. |
| Mode | Connection | Select 'Connection' for paths, and 'Movement'. The 'Movement' option is only available using a 'Pixel' display mode. |
| Display |  Vector (Interact) | The 'Vector (Interact)' display mode uses SVG elements to display the visualisation. The 'Pixel (Performance)' display mode uses a canvas to display the visualisation. When dealing with larg amounts of data, the pixel display mode will give better performance. |

###### Advanced

| Name | Default value | Accepted values | Description |
| -- | -- | -- |
| `move_continuous` | `true` | `true` / `false` | Allow for a single move or a coninuous move. |
| `move_retain` | `false` | `false` / single / all | Retain moving dots if Object is removed. |
| `move_unit` | pixel | pixel / day | Movemenent speed is based on distance in pixels or chronological distance. |
| `move_chronological` | `false` | `true` / `false` | Sets `move_continuous` to `false`, `move_retain` to `false` and	`move_unit` to 'day'. Allows the visualisation to be played chronologically. |
| `move_speed` | 30 | [_integer_] | Units per second. |
| `move_duration_min` | `false` | `false` / [_integer_] | Minimal duration of a moving dot. |
| `move_duration_max` | `false` | `false` / [_integer_] | Maximum duration of a moving dot. |
| `move_duration_info_min` | `false` | `false` / [_integer_] | Seconds. |
| `move_duration_info_max` | `false` | `false` / [_integer_] | Seconds. |
| `move_glow` | `false` | `true`/`false` | tba |
| `connection_line_opacity` | 0.4 | 0 - 1 | Default opacity of the lines connecting nodes. |
| `connection_line_opacity_range_min` | 0.5 | 0 - 1 | Minimal opacity of the lines connecting nodes. |
| `connection_line_opacity_range_max` | 1 | 0 - 1 | Maximum opacity of the lines connecting nodes. |
| `move_connection_line_apply_opacity` | moved | move / moved | tba |
| `move_warp_length` | 8 | [_integer_] | tba |
| `hint_dot` | pulse | `false`/ pulse / location | tba |
| `move_hint_dot` | `false` | `true` / `false` | tba |
| `moved_hint_dot` | `false` | `true` / `false` | tba |
| `hint_line` | `false` | `true` / `false` | tba |
| `moved_hint_line` | `false` | `true` / `false` | tba |
| `max_hint_dots` | 100 | [_integer_] | tba |
| `dot_icon` | circle | circle / square | Set to square to show nodes as squares. |
| `info_show` | `false` | `true` / `false`/ [_integer_] | Sets info_show_dot and info_show_line. |
| `info_show_dot` | `false` | `true` / `false`/ [_integer_] | Set to `true` to show info per dot. Set integer to maximise amount of info shown. |
| `info_show_line` | `false` | `true` / `false`/ [_integer_] | Set to `true` to show info per line. Set integer to maximise amount of info shown. |
| `info_color` | #000000 | [_hexadecimal color value_] | Colour of info. |
| `info_mode` | all | all/hover | Set to hover to only show info on hover. |
| `info_condition` | `false` | `false`/ [_condition name_] | Set condition name that shows info. |


#### Social

##### Design

| Name  | Default value | Description |
| -- | -- | -- |
| Dot Colour | #ffffff | Colour of nodes |
| Dot Min Size | 3 | Minimal size of nodes. |
| Dot Max Size | 20 | Maximum size of nodes. |
| Dot Stroke Colour | #aaaaaa | Colour of stroke of nodes. |
| Dot Stroke Width | 1 | Width of stroke of nodes. |
| Show Arrowhead | No | Include arrowheads for lines |

##### Settings

| Name  | Default value | Description |
| -- | -- | -- |
| Include Location References | No | Display Location References as nodes |
| Background Colour | none | Background colour of the visualisation |
| Display | Vector (Interact) | The 'Vector (Interact)' display mode uses SVG elements to display the visualisation. The 'Pixel (Performance)' display mode uses a canvas to display the visualisation. When dealing with larg amounts of data, the pixel display mode will give better performance. |
| Static Layout | No | Display static layouts |
| Static Layout Interval | none | Inteval in seconds between static layout renderings |

###### Advanced

| Name | Default value | Accepted values | Description |
| -- | -- | -- |
| `force_friction` | 0.9 | 0 - 1 | [info](https://github.com/d3/d3-3.x-api-reference/blob/master/Force-Layout.md#friction) |
| `force_charge` | -100 | [_integer_] | [info](https://github.com/d3/d3-3.x-api-reference/blob/master/Force-Layout.md#charge) |
| `force_gravity` | 0.08 | 0 - 1 | [info](https://github.com/d3/d3-3.x-api-reference/blob/master/Force-Layout.md#gravity) |
| `force_theta` | 0.8 | 0 - 1 | [info](https://github.com/d3/d3-3.x-api-reference/blob/master/Force-Layout.md#theta) |
| `label_threshold` | 0.1 | 0 - 1 | Threshold of labels to be shown. |