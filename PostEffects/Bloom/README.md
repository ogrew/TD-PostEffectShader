# Bloom

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115397242-d91ad680-a220-11eb-88cb-9c852e1b5468.JPG)

## Shader Code

```glsl
uniform int xRange;
uniform int yRange;

out vec4 fragColor;

void main()
{
    vec4 sum = vec4(0);
    vec2 uv = vUV.st;
    
    for(int i = -yRange; i < yRange; i++) {
        for(int j = -xRange; j < xRange; j++) {
            sum += texture(sTD2DInputs[0], uv + vec2(j,i)*0.005) * 0.25;
        }
    }

    vec4 color = vec4(0);
    float red = texture(sTD2DInputs[0], uv).r;

    if(red < 0.3) {
        color = sum*sum*0.012 + texture(sTD2DInputs[0], uv);
    } else if(red < 0.5)  {
        color = sum*sum*0.009 + texture(sTD2DInputs[0], uv);
    } else {
        color = sum*sum*0.0075 + texture(sTD2DInputs[0], uv);
    }
    
    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![Bloom](https://user-images.githubusercontent.com/21966381/115664687-1c8a5780-a37d-11eb-984c-0c7f6c60d800.jpg)

## Reference

https://github.com/spite/Wagner/blob/master/fragment-shaders/bloom-fs.glsl
