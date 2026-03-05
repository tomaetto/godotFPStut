today i did:

i want my player to decelerate before stopping for inertia
	so i copied some lerp stuff into the else: when up is not pressed

i want my players fov to grow when moving faster speed  when sprinting
	const base_fov for walking fov
	const fov change for when fov grows

		i made math for fov to grow when sprinting
		var velocity_clamped = clamp(velocity.length(), 8.5, SPRINT_SPEED * 2)
		var target_fov = BASE_FOV + FOV_CHANGE * velocity_clamped
		camera.fov = lerp(camera.fov, target_fov, delta * 8.0)

in my own words of how this works:

	"velocity speed is clamped so that camera does not go crazy when:
	say a player falls and velocity goes too high"
		
	target_fov = base fov increases when sprinting,clamped
	camera.fov = lerp mathed target_fov

comentary: i spent a few hours learning how the lerp that i built worked

when i say mathed i mean that i did without understanding how i did
lerp/linearInterpolation, method for slick transit of values over time

when i do math i don't think, it flows out like instinct hence mathed
i know enough to use lerp but not enough to explain how i used lerp.