# Kaleidoscope

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397366-f9e32c00-a220-11eb-84ef-bbf6805fcb9f.JPG)

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

![Kaleidoscope](https://user-images.githubusercontent.com/21966381/115665834-c6b6af00-a37e-11eb-9b2c-a4f39870de70.gif)
