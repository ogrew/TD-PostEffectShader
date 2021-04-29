# Triangle Mosaic

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/116586865-dde43680-a954-11eb-8fda-b8eee8faa283.JPG)

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

![TriangleMosaic](https://user-images.githubusercontent.com/21966381/116586869-de7ccd00-a954-11eb-9c47-8de45e6c2022.jpg)

## Reference

https://www.shadertoy.com/view/4d2SWy
