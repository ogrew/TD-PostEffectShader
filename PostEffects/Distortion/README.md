# Distortion

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397266-df10b780-a220-11eb-8f15-193b45f663cf.JPG)

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