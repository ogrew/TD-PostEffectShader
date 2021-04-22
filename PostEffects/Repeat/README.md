# Repeat

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397517-25fead00-a221-11eb-848b-aea0e1c93171.JPG)

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

![Repeat](https://user-images.githubusercontent.com/21966381/115665124-c0740300-a37d-11eb-8329-afd2e7e2216a.jpg)
