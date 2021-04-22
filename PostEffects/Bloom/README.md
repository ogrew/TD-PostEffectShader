# Bloom

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397242-d91ad680-a220-11eb-88cb-9c852e1b5468.JPG)

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

![Bloom](https://user-images.githubusercontent.com/21966381/115664687-1c8a5780-a37d-11eb-984c-0c7f6c60d800.jpg)
