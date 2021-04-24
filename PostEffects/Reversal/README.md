# Reversal

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397646-4c244d00-a221-11eb-83c6-78fcd4fcfaf7.JPG)

## Shader Code

```glsl
out vec4 fragColor;

void main()
{
    vec4 color = texture(sTD2DInputs[0], vUV.st);
    color = vec4(vec3(1.0) - color.rgb, 1.0);

    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![Reversal](https://user-images.githubusercontent.com/21966381/115665146-c9fd6b00-a37d-11eb-841a-032bd8a248a0.jpg)

## Reference

https://ics.media/entry/5535/
