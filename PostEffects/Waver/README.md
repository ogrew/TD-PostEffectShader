# Waver

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397400-05365780-a221-11eb-878e-8c9b0454edd5.JPG)

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

![Waver](https://user-images.githubusercontent.com/21966381/115665963-e948c800-a37e-11eb-811a-d595ede08e1e.gif)
