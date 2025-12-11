```
extends Node2D

@export var angle = deg_to_rad(35)
@export var distance = 200

@onready var obj1 = $"1"
@onready var obj2 = $"2"

func _physics_process(delta: float) -> void:
	obj2.position = Vector2(
	obj1.position.x + cos(angle) * distance,
	obj1.position.y + sin(angle) * distance
	)
	angle = deg_to_rad($HSlider.value)
	$HSlider/Label.text = str(int($HSlider.value))
	distance = $HSlider2.value
	$HSlider2/Label.text = str(int($HSlider2.value))
	
	$Label.text = "x: cos(%.5f) y: sin(%.5f)" % [angle, angle]
```
