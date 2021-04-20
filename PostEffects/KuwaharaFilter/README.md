# Kuwahara Filter

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397319-ed5ed380-a220-11eb-96aa-4af83ee7e6c3.JPG)

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