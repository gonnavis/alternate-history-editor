## Development

### Bugs
- Some scenarios have data corruptions which means counts of regions for labels are not necessarily correct
- Loaded scenarios are not copied into map, instead modified directly, this means reloading the scenario will load the modified version of this, recode so this isn't the case, i.e. loading scenario is by copy not by calling upon the scenario data directly

### General
- Leaflet 1.6.0 was used
- To add more premade scenarios to app, first create a save of the scenario using the app, then turn to js form (see existing ones for example; effectively you turn the json object into an exportable object in a js file, quite simple, just declare the object as a variable and add export in front), then go to scenario_loader.js to add in relevant initialisation code

### Possible future additional changes (unlikely though in the near future)
- Timeline features
	- Allow shuffling timeline entry order around
	- Allow timeline entry duplication
	- Allow entry adding that doesn't inherit previous as well for non timeline maps
- Map
	- Change colours from legend/select regions of same colour; perhaps use leaflet search?
	- On map label functionality
	- Different map layers (e.g. terrain, population density, etc.)
	- Statistics page for evaluations of say number of regions under a colour, etc.
	- Don't render borders when zoomed far out for ease of view
	- Highlight all regions belonging to the legend entry when hovering over legend
- Colouring
	- Styling polygons with images and patterns other than pure colours (should be a plugin somewhere)
- General
	- Some older scenarios contain data bugs due to being made at older time, hence legend may keep displaying label despite no region having them; probably establish a save fixer algorithm in load that mends this issue by parsing through existing regions and changing region counts accordingly
	- Allow arrow key switching between timeline entries
	- Get a better interface theme
	- Integrate common additional basemaps
	- Refactor code to reduce coupling, and finish up those optional todos
  		- Ideally focus more on functional programming ideas and focus on pure functions and separate data and gui to avoid coupling
	- Try to move help content into on the page assistance as reading help is really cumbersome
	- Make scenario loading download from github not all initialised directly as that way, if too many sceanrios, will crunch up memory
