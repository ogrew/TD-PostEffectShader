# Distortion

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397266-df10b780-a220-11eb-8f15-193b45f663cf.JPG)

## Shader Code

```glsl
uniform float scale;
uniform vec2 center;

out vec4 fragColor;
void main()
{
    vec2 direction = vUV.st - center;
    vec2 coord = vUV.st + scale * normalize(direction);
    vec4 color = texture(sTD2DInputs[0], coord);

    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![Distortion](https://user-images.githubusercontent.com/21966381/115664727-2c09a080-a37d-11eb-91c2-5f72e1b04158.jpg)
