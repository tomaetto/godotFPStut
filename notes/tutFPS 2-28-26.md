today i did:


"I'll use the math knowledge from a 10th grade algebra class that I thought i'll never use"
"The math of sine and cosine in laymans terms 'how waves go up and down' "

"I want head to bob to footsteps like in horror games. I will use a sine wave func to achieve this"

	set const BOB_FREQ for how often head bobs, supposed to be movement 
	I set and BOB_AMP for how far head moves when it bobs.
	I set var t_bob to tick where i'm at on the sine wave func
	
	"i made the tick math" t_bob + delta * velocity.length() * is_on_floor()
		delta is how much time since last bob
		velocity.length() to make head bob more when player is faster
		is_on_floor() so head doesn't bob when not on floor jump etc

	i made func _headbob where camera position trans forms to sine wave math
	
		camera.transform.origin = _headbob(t_bob)
		
		func _headbob(time) -> Vector3:
			var pos = Vector3.ZERO
			pos.y = sin(time * BOB_FREQ) * BOB_AMP
			pos.x = cos(time * BOB_FREQ / 2) * BOB_AMP
			return pos

		"I barely understand this but in my words"
			"using the above tick math to know where i'm at" t_bob knows it's at
			"I take Vector3/zAxis ithink not sure" Then do sin math up & down
			sine(time"might be delta not sure" * FREQ) * AMP"makes head move"
			cosine(time * FREQ/2"This happens less often then above") * AMP
			 Cos makes head bob horizonal but is not tied to horizontal movement

	"I added bobbing for a Doom vibe"

"I will add sprint for player"
	
	i changed SPEED to a var
	i added const for WALK=5 and SPRINT=8 SPEEDs

	i added and if else to check if I'm pressing shift
		if pressed speed = sprint
		else speed = walk

"Theres bug/not really when jumping i can pause in the air mid jump before falling"
"this breaks momentum or flow, i will add inertia to fix this to accomplish inertia:
the player should have reduced control of airborne movement"

	i put the directional controls under if is_on_floor
		in the else i used lerp for momentum
		i don't understand lerp math but according to the program it sums up to:
		"if you were fast on the ground and jump,
		 you'll keep that speed & direction while airborne until grounded again"
