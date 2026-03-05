today i did:

	i want an fps so i made a scene3d/world
		i added csgboxes to make floor, walls terrain then enabled collision"
			i change color in rgb in csgbox3d properties
			 Geometry/materialoverride/standardMaterial/Albedo

		i added directional light/sun
			 "Don't worry about lighting until designing scenes"
	
	a game needs a player so characterbody3d/player
		added meshInstanceCapsule with Collision Shape "Must be uniform"
		
		added Camera as child of Node34/Head
			 "Camera needs pivot point/head or weird happens"
		
		i added gdscript from the engine for simple movement to player
	
	Coding in player.gd
	
		"Cursor should'nt be visible when game runs" MOUSE_MODE_CAPTURED
			To close running game without cursor press F
	
		"Player Needs to look around with mouse"
			I defined nodes head and camera as onready vars 
				"I dragged the nodes from sceneview instead of typing the path"

			I want mouse to control camera so input is InputEventMouseMotion
				"Also works with touchpad"
			relative*SENSITIVITY "SENSITIVITY is set to 0.02"

			bugs i found
				Bug Camera should not cartwheel 
					fix use camera rotation with clamp
				Bug Body does not move forward where camera is facing
					fix chang direction from default/players mesh to head
					var direction = (head.transform.basis

		In project settings because of good paractice comment
		inputmap mapped simple movements for playes to wsad etc for player.gd