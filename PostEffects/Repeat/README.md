# Repeat

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397517-25fead00-a221-11eb-848b-aea0e1c93171.JPG)

## Shader Code

```glsl
uniform vec2 scale;

out vec4 fragColor;

void main()
{
    vec2 uv = vUV.st;
    uv.x *= scale.x;
    uv.y *= scale.y;

    vec4 color = texture(sTD2DInputs[0], uv);
    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![Repeat](https://user-images.githubusercontent.com/21966381/115665124-c0740300-a37d-11eb-8329-afd2e7e2216a.jpg)

## Reference

https://scrapbox.io/sayachang/%E3%81%8B%E3%82%93%E3%81%9F%E3%82%93%E3%82%A8%E3%83%95%E3%82%A7%E3%82%AF%E3%83%88%E5%8A%A0%E5%B7%A5%E3%82%B7%E3%82%A7%E3%83%BC%E3%83%80%E3%83%BC
