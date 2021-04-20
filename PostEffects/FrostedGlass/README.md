# Frosted Glass

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397744-63fbd100-a221-11eb-8916-9830be5ecc6c.JPG)

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