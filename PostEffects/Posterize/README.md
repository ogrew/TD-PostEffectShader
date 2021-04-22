# Posterize

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397719-5d6d5980-a221-11eb-96f0-a7694c027272.JPG)

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

![Posterize](https://user-images.githubusercontent.com/21966381/115665102-b81bc800-a37d-11eb-9441-2b2bf2312a63.jpg)
