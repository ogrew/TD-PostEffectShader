# Scroll

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397601-3dd63100-a221-11eb-89bc-ef2b3bc9a5b1.JPG)

## Shader Code

```glsl
uniform vec2 time;

out vec4 fragColor;

void main()
{
    vec2 uv = vUV.st;

    uv.x += fract(sin(time.x));
    uv.y += fract(sin(time.y));

    vec4 color = texture(sTD2DInputs[0], uv);

    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![Scroll](https://user-images.githubusercontent.com/21966381/115666332-6a07c400-a37f-11eb-9c2d-be92ac972319.gif)

## Reference

https://scrapbox.io/sayachang/%E3%81%8B%E3%82%93%E3%81%9F%E3%82%93%E3%82%A8%E3%83%95%E3%82%A7%E3%82%AF%E3%83%88%E5%8A%A0%E5%B7%A5%E3%82%B7%E3%82%A7%E3%83%BC%E3%83%80%E3%83%BC
