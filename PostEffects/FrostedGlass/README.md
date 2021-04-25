# Frosted Glass

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115987270-56fb2b00-a5ef-11eb-9150-381ab2aa1c2b.jpg)

## Shader Code

```glsl
uniform float size;

out vec4 fragColor;

float rand(vec2 st){
    return fract(sin(dot(st.xy ,vec2(12.9898,78.233))) * 43758.5453);
}

void main()
{
    vec4 color = texture(sTD2DInputs[0], vUV.st);

	vec2 uv;
    uv.x = (vUV.s * uTD2DInfos[0].res.z) + rand(vUV.st) * size * 2. - size;
    uv.y = (vUV.t * uTD2DInfos[0].res.w) + rand(vUV.ts) * size * 2. - size;

    color = texture(sTD2DInputs[0], uv/uTD2DInfos[0].res.zw);
    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![FrostedGlass](https://user-images.githubusercontent.com/21966381/115664743-30ce5480-a37d-11eb-8483-4ea7755edabb.jpg)

## Reference

https://ics.media/entry/5535/
