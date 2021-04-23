# Water Ripple

## Properties

![Properties](https://user-images.githubusercontent.com/21966381/115899261-7da74d80-a499-11eb-9327-30a4960743c7.JPG)

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

![WaterRipple](https://user-images.githubusercontent.com/21966381/115899255-7bdd8a00-a499-11eb-9b85-dc2e41cfc6f5.gif)
