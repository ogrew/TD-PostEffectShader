# Halftone

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115436693-3bd29900-a246-11eb-997a-454ebcb529d2.JPG)

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

![Halftone](https://user-images.githubusercontent.com/21966381/115664757-362b9f00-a37d-11eb-96c9-ea838401a7a2.jpg)
