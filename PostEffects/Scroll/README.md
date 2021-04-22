# RGB Split

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397601-3dd63100-a221-11eb-89bc-ef2b3bc9a5b1.JPG)

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

![Scroll](https://user-images.githubusercontent.com/21966381/115666332-6a07c400-a37f-11eb-9c2d-be92ac972319.gif)
