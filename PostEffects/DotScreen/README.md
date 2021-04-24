# Dot Screen

## Properties

![Properties](https://user-images.githubusercontent.com/21966381/115966955-e5799900-a56a-11eb-9ea8-6134796b9eba.JPG)

## Shader Code

```glsl
uniform vec2 center;
uniform float angle;
uniform float scale;
const float PI = 3.141592653589793;

out vec4 fragColor;

float pattern() {
    float s = sin(angle);
    float c = cos(angle);
    vec2 uv = vUV.st * uTD2DInfos[0].res.zw - center;
    vec2 point = vec2(
        c * uv.x - s * uv.y,
        s * uv.x + c * uv.y
    ) * PI/scale;

    return (sin(point.x) * sin(point.y)) * 4.0;
}

void main() {
    vec4 color = texture(sTD2DInputs[0], vUV.st);
    float average = (color.r + color.g + color.b) / 3.0;
    color = vec4( vec3(average) * 10.0 - 5.0 + pattern(), 1.0);
    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![DotScreen](https://user-images.githubusercontent.com/21966381/115966954-e4486c00-a56a-11eb-8d55-60b46b27f92c.jpg)

## Reference

https://github.com/evanw/glfx.js/blob/master/src/filters/fun/dotscreen.js
