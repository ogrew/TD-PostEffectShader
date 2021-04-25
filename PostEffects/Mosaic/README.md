# Mosaic

## Properties

![Properties](https://user-images.githubusercontent.com/21966381/115987091-9117fd00-a5ee-11eb-9e16-bb3107321f36.jpg)


## Shader Code

```glsl
uniform float scale;

out vec4 fragColor;

void main()
{
	vec2 d = uTD2DInfos[0].res.zw / scale;
    vec2 uv = floor(vUV.st * d) / d + (scale / 2.) / uTD2DInfos[0].res.zw;
    vec4 color = texture(sTD2DInputs[0], uv);

    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![Mosaic](https://user-images.githubusercontent.com/21966381/115665091-b520d780-a37d-11eb-8b39-690660cdc894.jpg)

## Reference

https://ics.media/entry/5535/
