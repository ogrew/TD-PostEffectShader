# Triangle Mosaic

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397794-71b15680-a221-11eb-9885-e52a98fb4542.JPG)

## Shader Code

```glsl
uniform float scaleX;
uniform float scaleY;

out vec4 fragColor;

void main()
{
    vec2 uv = vUV.st;
	vec2 scale = vec2(scaleX, scaleY);
    vec2 uv2 = floor(uv * scale) / scale;
    uv -= uv2;
    uv *= scale;

    vec4 color = texture(sTD2DInputs[0],  
                        uv2 + vec2(
                                step(1.0 - uv.t, uv.s) / (2.0 * scaleX),
                                step(uv.s, uv.t) / (2.0 * scaleY)));

    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![Templete](https://user-images.githubusercontent.com/21966381/115665440-48f2a380-a37e-11eb-8693-3b70fdd8b2fc.jpg)

## Reference

https://www.shadertoy.com/view/4d2SWy
