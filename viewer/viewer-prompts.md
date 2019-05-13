## Copy/Paste into your developer console for results
Please refer to https://forge.autodesk.com/en/docs/viewer/v6/reference for more

1. NOP_VIEWER.model.getData().instanceTree  // Returns geometry data
2. NOP_VIEWER.getAggregateSelection() 	// Returns dbId’s of selected objects in viewer
3. NOP_VIEWER.isolate([24]) // Give it array of dbId's to isolate
4. NOP_VIEWER.hide([24])  // Hide dbIds array
5. NOP_VIEWER.setGroundReflection(true) // Turn on/off ground reflection
6. Set color for an object in the scene
    a) let color = new THREE.Vector4(0, 0.8901960784313725, 0, .9)
    b) NOP_VIEWER.setThemingColor(24, color)
7. Setting the camera position:
    a) NOP_VIEWER.impl.camera // Firstly, align camera in viewer, then get camera position 
    b) Store camera in variable _camera_ as follows:
    ```
    var camera = {
        fov:          53.13010235415598,
        isPerspective:true,
        orthoScale:   6.442020414517138,
        position:     {x:-23.63091853857176, y: 0.9033896546012906, z:-4.261154219883789},
        target:       {x:-20.871083468967406, y: 6.520671770079398, z:-5.787286273399167},
        up:           {x:0.10446560472788749, y: 0.21262602957092375, z:0.9715333802694284}
    }
    ```
    c) NOP_VIEWER.impl.setViewFromCamera(camera, true) // Set the camera position
