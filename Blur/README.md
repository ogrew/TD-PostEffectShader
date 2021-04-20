# Blur

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397427-0bc4cf00-a221-11eb-97bd-536d806092d6.JPG)

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