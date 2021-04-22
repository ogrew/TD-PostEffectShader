# Templete

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397794-71b15680-a221-11eb-9885-e52a98fb4542.JPG)

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

![Templete](https://user-images.githubusercontent.com/21966381/115665440-48f2a380-a37e-11eb-8693-3b70fdd8b2fc.jpg)
