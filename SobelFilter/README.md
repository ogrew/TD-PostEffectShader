# Sobel Filter

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397542-2f881500-a221-11eb-99ee-f03c5b881fa4.JPG)

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