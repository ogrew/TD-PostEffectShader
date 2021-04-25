# RGB Split

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115987133-b3aa1600-a5ee-11eb-9409-19ff7e31e98c.jpg)

## Shader Code

```glsl
uniform float amount;

out vec4 fragColor;

void main()
{
    vec4 color = texture(sTD2DInputs[0], vUV.st);
    
    vec2 res = uTD2DInfos[0].res.zw;
    vec2 val = amount * (res - gl_FragCoord.xy) / res;
    
    vec4 c1 = texture(sTD2DInputs[0], vUV.st - val / res.x);
    vec4 c2 = texture(sTD2DInputs[0], vUV.st);
    vec4 c3 = texture(sTD2DInputs[0], vUV.st + val / res.y);
    
    color = vec4(c1.r, c2.g, c3.b, c1.a + c2.a + c3.a);

    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![RGBSplit](https://user-images.githubusercontent.com/21966381/115665164-d1247900-a37d-11eb-9582-9c92fcb16562.jpg)

## Reference

https://github.com/spite/Wagner/blob/master/fragment-shaders/rgb-split-fs.glsl
