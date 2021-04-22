# RGB Split

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397191-cbfde780-a220-11eb-9866-8bca851a3479.JPG)

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

![Sharpen](https://user-images.githubusercontent.com/21966381/115665362-2c566b80-a37e-11eb-9fa8-900a5b1252d6.jpg)
