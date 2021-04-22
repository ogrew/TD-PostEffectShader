# Vignette

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397623-4464a880-a221-11eb-8a54-2e750513af45.JPG)

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

![Vignette](https://user-images.githubusercontent.com/21966381/115665456-4c862a80-a37e-11eb-8b47-ea33625859bb.jpg)
