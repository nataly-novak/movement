extends Node2D

var x0 = 0.0
var y0 = 0.0
var v0x = 0.0
var v0y = 0.0
var g = 9.8
var x = 0.0
var y = 0.0
var vx = 0.0
var vy = 0.0
var v0 = 0.0
var v = 0.0
var alpha = 0.0
var beta = 0.0
var is_active = false
var t = 0
var h = 0

# Called when the node enters the scene tree for the first time.
func _ready():
	pass # Replace with function body.


# Called every frame. 'delta' is the elapsed time since the previous frame.
func _process(delta):
	if is_active:
		t = t+delta
		x = x0+v0x*t
		y = y0+v0y*t-g*t*t/2
		vx = v0x
		vy = v0y - g*t
		v = sqrt(vx*vx + vy*vy)
		beta = atan(vy/vx)*180/PI
		if y>h:
			h = y
		$background/input/i6/text.text = str(x)
		$background/input/i7/text.text = str(y)
		$background/input/i8/text.text = str(v)
		$background/input/i9/text.text = str(beta)
		$background/input/i10/text.text = str(h)
		$background/ball.position.y = 600-32-y*100
		$background/ball.position.x = 300+x*100
		if y < -0.02:
			is_active = false
		
		


func _on_start_pressed():
	x0 = float($background/input/i1/text.text)
	y0 = float($background/input/i2/text.text)
	v0 = float($background/input/i3/text.text)
	alpha = float($background/input/i4/text.text)
	g = float($background/input/i5/text.text)
	x = x0
	y = y0
	v0x = v0*cos(alpha/180*PI)
	print(cos(alpha/180*PI))
	v0y = v0*sin(alpha/180*PI)
	print(vy)
	t = 0
	is_active = true
	$background/ball.position.y = 600-32-y*100
	$background/ball.position.x = 300+x*100

func _on_pause_pressed():
	is_active = not(is_active)
	if is_active:
		$background/input/pause.text = "Pause"
	else:
		$background/input/pause.text = "Resume"


