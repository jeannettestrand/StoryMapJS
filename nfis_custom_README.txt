This file describes the customizations made to the StoryMapJS library for NFIS use. 

FEATURE: WMS Layers
	DESCRIPTION: 
		This feature allows a user to load layers from a WMS service to their storymap. The user 
		indicates the WMS service and layers using an object value for the map_type parameter. 
		
		This feature is available to users who are building a StoryMap outside of the authoring
		tool. 

	PARAMETERS:
		This feature piggy-backs an object containing information for the WMS Service on the existing
		map_type parameter. This parameter will still accept a string for simple map services like OSM. 
		
		The object will contain url & options keys. URL will take a string of the WMS service url
		prepended with "wms:". Options will take an object with key/value pairs providing additional
		parameters to the WMS service. 

		Example of a valid map_type parameter loaded with WMS service. 
		 "map_type": {
       			"url":"wms:https://pfc.cfsnet.nfis.org/mapserver/cgi-bin/cafgris_littles_fr.cgi?",
       			"options":{"layers": "thujplic,pinucont", "transparent":true, "format":"image/png"}
     		}
	CHANGESET: 
		commit: b1869f6cd11272b367ef2b95ebae5b0a1d780bde
		title:  Load base map and map layers on map initialization 
		user: jeannettestrand
	
FEATURE: Base Map
	DESCRIPTION:
		This feature allows a user to load a base map in addition to Map layers on their storymap. The
		user indicates the type of basemap using a new parameter called "base_map". The value of this 
		parameter can be any of the valid values for "map_type". 

		This feature is available to users who are building a StoryMap outside of the authoring tool. 

	PARAMETERS:
		This feature introduces a new parameter titled "base_map". The user can provide any value valid
		for map_type to "base_map". 
		
		Example of a valide base_map parameter:
		"base_map":{
       			"url": "osm:standard"
     		}
	CHANGESET: 
		commit: b1869f6cd11272b367ef2b95ebae5b0a1d780bde
                title:  Load base map and map layers on map initialization
                user: jeannettestrand		
