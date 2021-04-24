# Waver

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397400-05365780-a221-11eb-878e-8c9b0454edd5.JPG)

## Shader Code

```glsl
uniform float time;
uniform vec2 speed;
uniform vec2 length;
uniform vec2 width;

out vec4 fragColor;

float Offset(float pos, float length, float width, float speed) {
    return sin(pos * length + mod(time, 3.0) * speed) * width;
}

void main()
{

    float offsetX = Offset(vUV.s, length[0], width[0], speed[0]);
    float offsetY = Offset(vUV.t, length[1], width[1], speed[1]); 

    vec2 uv = vUV.st + vec2(offsetX, offsetY);

    vec4 color = texture(sTD2DInputs[0], uv); 
    fragColor = TDOutputSwizzle(vec4(color.rgb, 1.0));
}
```

## Gallery

![Waver](https://user-images.githubusercontent.com/21966381/115665963-e948c800-a37e-11eb-811a-d595ede08e1e.gif)

## Reference

https://nogson2.hatenablog.com/entry/2018/01/19/002342
