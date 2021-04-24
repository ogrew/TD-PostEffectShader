# Barrel Distortion

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397498-1da67200-a221-11eb-8062-cb3d08b284b1.JPG)

## Shader Code

```glsl
uniform float scale;
uniform float power;
out vec4 fragColor;

void main()
{
    vec2 center = 2.0* vUV.st - vec2(1.0);
    float barrel = min(1.0 - length(center)*scale, 1.0) * power;
    vec2 pos = vUV.st - center * barrel;

    vec4 color = texture(sTD2DInputs[0], pos);
    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![BarrelDistortion](https://user-images.githubusercontent.com/21966381/115664661-14cab300-a37d-11eb-8097-07bcda508c47.jpg)

## Reference

https://scrapbox.io/sayachang/%E3%81%8B%E3%82%93%E3%81%9F%E3%82%93%E3%82%A8%E3%83%95%E3%82%A7%E3%82%AF%E3%83%88%E5%8A%A0%E5%B7%A5%E3%82%B7%E3%82%A7%E3%83%BC%E3%83%80%E3%83%BC
