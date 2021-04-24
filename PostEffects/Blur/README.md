# Blur

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397427-0bc4cf00-a221-11eb-97bd-536d806092d6.JPG)

## Shader Code

### <Quarter downsampler>
```glsl
out vec4 fragColor;

void main()
{
    vec2 res = uTD2DInfos[0].res.zw;
    vec4 dir = res.xyxy * vec4(1, 1, -1, -1);
    vec4 color = vec4(0.0);
    color  = texture(sTD2DInputs[0], vUV.st + dir.xy);
    color += texture(sTD2DInputs[0], vUV.st + dir.xw);
    color += texture(sTD2DInputs[0], vUV.st + dir.zy);
    color += texture(sTD2DInputs[0], vUV.st + dir.zw);
    color *= 0.25;

    fragColor = TDOutputSwizzle(color);
}
```

### <Horizontal>
```glsl
uniform float size;

out vec4 fragColor;

void main()
{
	vec2 dir = vec2(size, 0.0);
    vec2 res = uTD2DInfos[0].res.zw;
    vec4 color = texture(sTD2DInputs[0], vUV.st) * 0.227027027;

    vec2 d1 = dir * vec2(1.3846153846);
    color += texture(sTD2DInputs[0], vUV.st + d1/res) * 0.3162162162;
    color += texture(sTD2DInputs[0], vUV.st - d1/res) * 0.3162162162;

    vec2 d2 = dir * vec2(3.2307692308);
    color += texture(sTD2DInputs[0], vUV.st + d2/res) * 0.0702702703;
    color += texture(sTD2DInputs[0], vUV.st - d2/res) * 0.0702702703;

    fragColor = TDOutputSwizzle(color);
}
```

### <Vertical>
```glsl
uniform float size;

out vec4 fragColor;

void main()
{
	vec2 dir = vec2(0.0, size);
    vec2 res = uTD2DInfos[0].res.zw;
    vec4 color = texture(sTD2DInputs[0], vUV.st) * 0.227027027;

    vec2 d1 = dir * vec2(1.3846153846);
    color += texture(sTD2DInputs[0], vUV.st + d1/res) * 0.3162162162;
    color += texture(sTD2DInputs[0], vUV.st - d1/res) * 0.3162162162;

    vec2 d2 = dir * vec2(3.2307692308);
    color += texture(sTD2DInputs[0], vUV.st + d2/res) * 0.0702702703;
    color += texture(sTD2DInputs[0], vUV.st - d2/res) * 0.0702702703;

    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![GaussianBlur](https://user-images.githubusercontent.com/21966381/115664697-20b67500-a37d-11eb-9818-cf55bf9d5e3e.jpg)

## Reference

https://github.com/Jam3/glsl-fast-gaussian-blur/blob/master/9.glsl
