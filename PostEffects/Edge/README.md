# Edge (dFdx / dFdy)

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/119094028-6f723000-ba4b-11eb-9a07-8efd577861b1.JPG)

## Shader Code

```glsl
uniform float Boundary;

out vec4 fragColor;

// NTSC Coef. method
const vec3 monochrome = vec3(
        0.298912,
        0.586611,
        0.114478
);

void main(){
    vec2 uv = vUV.st;
    vec2 res = uTD2DInfos[0].res.zw; 
    vec4 color = texture(sTD2DInputs[0], uv);
    float gray = dot(color.rgb, monochrome);

    vec2 dF = vec2(dFdx(gray), dFdy(gray));
    vec3 edge = vec3(step(Boundary, length(dF)));

    color.rgb = edge;
    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![Edge](https://user-images.githubusercontent.com/21966381/119094026-6e410300-ba4b-11eb-9943-acde6ab219e5.jpg)

## Reference

https://qiita.com/gam0022/items/1342a91d0a6b16a3a9ba
