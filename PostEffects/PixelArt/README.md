# Pixel Art

## Properties

![Properties](https://user-images.githubusercontent.com/21966381/115894898-c4467900-a494-11eb-96f9-afbb017e15c0.JPG)

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

![PixelArt](https://user-images.githubusercontent.com/21966381/115894894-c27cb580-a494-11eb-813a-58e29bea00ec.jpg)
