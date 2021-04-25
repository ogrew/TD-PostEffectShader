# Sharpen

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115987348-a04b7a80-a5ef-11eb-9fa5-2dc5c128414e.jpg)

## Shader Code

```glsl
uniform float sharpness;

out vec4 fragColor;

void main()
{
    vec2 res = uTD2DInfos[0].res.zw;
    vec2 s = vec2(1.0/res.x, 1.0/res.y) * 1.5;
    
    vec4 blur = texture(sTD2DInputs[0], vUV.st + vec2(s.x, -s.y));
    blur += texture(sTD2DInputs[0], vUV.st + vec2(-s.x, -s.y));
    blur += texture(sTD2DInputs[0], vUV.st + vec2(s.x, s.y));
    blur += texture(sTD2DInputs[0], vUV.st + vec2(-s.x, s.y));
    blur /= 4.0;

    vec4 color = texture(sTD2DInputs[0], vUV.st);
    color += (color - blur) * sharpness;

    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![Sharpen](https://user-images.githubusercontent.com/21966381/115665362-2c566b80-a37e-11eb-9fa8-900a5b1252d6.jpg)

## Reference

https://github.com/QianMo/X-PostProcessing-Library/blob/master/Assets/X-PostProcessing/Effects/SharpenV2/Shader/SharpenV2.shader
