# Posterize

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397719-5d6d5980-a221-11eb-96f0-a7694c027272.JPG)

## Shader Code

```glsl
uniform vec3 level;
uniform float gamma;

out vec4 fragColor;

void main()
{
    vec3 c = texture(sTD2DInputs[0], vUV.st).rgb;
    c = floor(c * level) / (level - 1.0);

    if((c.r+c.g+c.b)/3 > (255/2)) {
        c = pow(c, vec3(1.0/gamma));
    }

    vec4 color = vec4(c, 1.0);
    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![Posterize](https://user-images.githubusercontent.com/21966381/115665102-b81bc800-a37d-11eb-9441-2b2bf2312a63.jpg)

## Reference

https://www.geeks3d.com/20091027/shader-library-posterization-post-processing-effect-glsl/
