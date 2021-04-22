# Radical Blur

## Properties

![Properties](https://user-images.githubusercontent.com/21966381/115687221-ed7fe000-a394-11eb-99d5-686e1cc5ff63.JPG)

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

![RadicalBlur](https://user-images.githubusercontent.com/21966381/115687227-eeb10d00-a394-11eb-9efc-d47a78dc785d.jpg)
