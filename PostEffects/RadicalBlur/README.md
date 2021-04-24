# Radical Blur

## Properties

![Properties](https://user-images.githubusercontent.com/21966381/115687221-ed7fe000-a394-11eb-99d5-686e1cc5ff63.JPG)

## Shader Code

```glsl
uniform vec2 center;
uniform float radius;
uniform float dist;
uniform float intensity;
uniform float count;

out vec4 fragColor;

void main()
{
    vec2 vec = vUV.st - center;
    float len = length(vec);
    float fade = smoothstep(0, radius, len);
    vec2 dir = normalize(vec) * dist;
    float factor = len * 0.1 * intensity;
    dir *= factor;

    vec4 sum = vec4(0.0);
    vec2 v = vec2(0.0);

    for(int i = 0; i < count; i++) {
        v = dir * i;
        sum += texture(sTD2DInputs[1], vUV.st + v);
        sum += texture(sTD2DInputs[1], vUV.st - v);
    }
    sum *= 1.0 / (count * 2.0);

    vec4 color = mix(texture(sTD2DInputs[0], vUV.st), sum, fade*intensity);
    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![RadicalBlur](https://user-images.githubusercontent.com/21966381/115687227-eeb10d00-a394-11eb-9efc-d47a78dc785d.jpg)

## Reference

https://www.programmersought.com/article/28254675788/
