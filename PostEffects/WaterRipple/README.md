# Water Ripple

## Properties

![Properties](https://user-images.githubusercontent.com/21966381/115899261-7da74d80-a499-11eb-9327-30a4960743c7.JPG)

## Shader Code

```glsl
uniform float time;
uniform vec2 center;
uniform float freq;
uniform float amount;
uniform float speed;
out vec4 fragColor;

void main()
{
    vec2 coord = vUV.st - center;
    float len = length(coord);

    vec2 uv = vUV.st + coord * amount * abs(cos(len*freq - time*speed)) / len;
    
    vec4 color = texture(sTD2DInputs[0], uv);
    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![WaterRipple](https://user-images.githubusercontent.com/21966381/115899255-7bdd8a00-a499-11eb-9b85-dc2e41cfc6f5.gif)

## Reference

https://github.com/rystylee/GLSLPostEffects/blob/master/pfx/ripple.frag
