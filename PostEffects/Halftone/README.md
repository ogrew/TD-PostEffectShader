# Halftone

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115436693-3bd29900-a246-11eb-997a-454ebcb529d2.JPG)

## Shader Code

```glsl
uniform float freq;

out vec4 fragColor;
const float PI = 3.141592;

vec2 rot(vec2 st, float angle) {
    return mat2(cos(angle), -sin(angle),
                sin(angle),  cos(angle)) * st;
}

float aastep(float threshold, float val) {
    float afwidth = 0.7 * length(vec2(dFdx(val), dFdy(val)));
    return smoothstep(threshold-afwidth, threshold+afwidth, val);
}

void main()
{
    vec3 tex = texture(sTD2DInputs[0], vUV.st).rgb;

    vec4 cmyk;
    cmyk.xyz = 1.0 - tex;
    cmyk.w = min(cmyk.x, min(cmyk.y, cmyk.z));
    cmyk.xyz -= cmyk.w;

    // The commonly used angles for the CMYK primaries are 
    // 15, 75, 0 and 45 degrees. 
    vec2 Kst = freq*rot(vUV.st, PI/4.0);
    vec2 Kuv = 2.0*fract(Kst)-1.0;
    float k = aastep(0.0, sqrt(cmyk.w)-length(Kuv));

    vec2 Cst = freq*rot(vUV.st, 15.0/180 * PI);
    vec2 Cuv = 2.0*fract(Cst)-1.0;
    float c = aastep(0.0, sqrt(cmyk.x)-length(Cuv));

    vec2 Mst = freq*rot(vUV.st, 75.0/180 * PI);
    vec2 Muv = 2.0*fract(Mst)-1.0;
    float m = aastep(0.0, sqrt(cmyk.y)-length(Muv));

    vec2 Yst = freq*vUV.st; // 0 deg
    vec2 Yuv = 2.0*fract(Yst)-1.0;
    float y = aastep(0.0, sqrt(cmyk.z)-length(Yuv));
 
    vec3 rgb = 1.0 - 0.9*vec3(c,m,y);
    rgb = mix(rgb, vec3(0.0), 0.85*k);

    vec4 color = vec4(rgb, 1.0);

    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![Halftone](https://user-images.githubusercontent.com/21966381/115664757-362b9f00-a37d-11eb-96c9-ea838401a7a2.jpg)

## Reference

https://weber.itn.liu.se/~stegu/webglshadertutorial/shadertutorial.html
