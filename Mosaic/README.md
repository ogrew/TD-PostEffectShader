# Mosaic

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397763-69f1b200-a221-11eb-9aec-31bb3c3bec77.JPG)

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