# Barrel Distortion

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397498-1da67200-a221-11eb-8062-cb3d08b284b1.JPG)

## Shader Code

```glsl
// Example Pixel Shader

// uniform float exampleUniform;

out vec4 fragColor;
void main()
{
	// vec4 color = texture(sTD2DInputs[0], vUV.st);
	vec4 color = vec4(1.0);
	fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![BarrelDistortion](https://user-images.githubusercontent.com/21966381/115664661-14cab300-a37d-11eb-8097-07bcda508c47.jpg)
