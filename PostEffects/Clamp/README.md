# Clamp

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397582-3747b980-a221-11eb-9626-84d9cedb49aa.JPG)

## Shader Code

```glsl
uniform float min;
uniform float max;

out vec4 fragColor;

void main()
{
    vec2 coord = clamp(vUV.st, min, max);
    vec4 color = texture(sTD2DInputs[0], coord);

    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![Clamp](https://user-images.githubusercontent.com/21966381/115664711-26ac5600-a37d-11eb-8bdc-e0513d02f1d7.jpg)
