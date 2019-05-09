## Copy/Paste into your developer console for results
Please refer to https://forge.autodesk.com/en/docs/viewer/v2/reference/javascript/model for more

1. NOP_VIEWER.model.getData().instanceTree	// Returns geometry data
2. NOP_VIEWER.getAggregateSelection() 		// Returns dbId’s of selected objects in viewer
3. NOP_VIEWER.isolate([24])			// Give it array of dbId's to isolate
4. NOP_VIEWER.hide([24])			// Hide dbIds array
5. NOP_VIEWER.setGroundReflection(true) 	// Turn on/off ground reflection
6. let color = new THREE.Vector4(0, 0.8901960784313725, 0, .9)
   NOP_VIEWER.setThemingColor(24, color) 	// Sets color on object
