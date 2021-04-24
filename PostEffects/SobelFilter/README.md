# Sobel Filter

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397542-2f881500-a221-11eb-99ee-f03c5b881fa4.JPG)

## Shader Code

```glsl
uniform float thickness;

out vec4 fragColor;

void main()
{
    vec4 color = texture(sTD2DInputs[0], vUV.st);

    vec2 p = vUV.st + thickness/uTD2DInfos[0].res.zw;
    vec2 q = vUV.st - thickness/uTD2DInfos[0].res.zw;
    
    vec4 edgeHorizon = vec4(0.0);
    edgeHorizon -= texture(sTD2DInputs[0], vec2(q.x, q.y))    * 1.0;
    edgeHorizon -= texture(sTD2DInputs[0], vec2(q.x, vUV.y))  * 2.0;
    edgeHorizon -= texture(sTD2DInputs[0], vec2(q.x, p.y))    * 1.0;
    edgeHorizon += texture(sTD2DInputs[0], vec2(p.x, q.y))    * 1.0;
    edgeHorizon += texture(sTD2DInputs[0], vec2(p.x, vUV.y))  * 2.0;
    edgeHorizon += texture(sTD2DInputs[0], vec2(p.x, p.y))    * 1.0;
    
    vec4 edgeVert = vec4(0.0);
    edgeVert -= texture(sTD2DInputs[0], vec2(q.x,   q.y)) * 1.0;
    edgeVert -= texture(sTD2DInputs[0], vec2(vUV.x, q.y)) * 2.0;
    edgeVert -= texture(sTD2DInputs[0], vec2(p.x,   q.y)) * 1.0;
    edgeVert += texture(sTD2DInputs[0], vec2(q.x,   p.y)) * 1.0;
    edgeVert += texture(sTD2DInputs[0], vec2(vUV.x, p.y)) * 2.0;
    edgeVert += texture(sTD2DInputs[0], vec2(p.x,   p.y)) * 1.0;
    
    vec3 edge = sqrt((edgeHorizon.rgb * edgeHorizon.rgb) 
    + (edgeVert.rgb * edgeVert.rgb));
  
  	color = vec4(edge, color.a);
  
    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![Sobel](https://user-images.githubusercontent.com/21966381/115665376-2fe9f280-a37e-11eb-8ec1-7dfce6dea43f.jpg)

## Reference

https://github.com/spite/Wagner/blob/master/fragment-shaders/sobel-fs.glsl
