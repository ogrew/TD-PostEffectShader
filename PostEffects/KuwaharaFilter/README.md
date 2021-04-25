# Kuwahara Filter

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115987246-3af78980-a5ef-11eb-913c-0b4ced002771.jpg)

## Shader Code

```glsl
uniform float size;

out vec4 fragColor;

void main()
{
    vec2 res = vec2(int(uTD2DInfos[0].res.z),int(uTD2DInfos[0].res.w));

    vec4[4] area = vec4[](
        vec4(1,size,1,size),
        vec4(-size,1,1,size),
        vec4(-size,1,-size,1),
        vec4(1,size,-size,1)
    );

    float val = (size+1) * (size+1);

    //A. upper right area
    vec3 ave_A = vec3(0.0);
    vec3 var_A = vec3(0.0);
    for(float i = area[0].x; i<=area[0].y; i++) {
        for(float j = area[0].z; j<=area[0].w; j++) {
            vec3 src = texture(sTD2DInputs[0], vUV.st + vec2(i,j)/res).rgb;
            ave_A += src;
            var_A += src*src;
        }
    }
    ave_A /= val;
    var_A = abs(var_A/val - ave_A*ave_A);

    //B. upper left area
    vec3 ave_B = vec3(0.0);
    vec3 var_B = vec3(0.0);
    for(float i = area[1].x; i<=area[1].y; i++) {
        for(float j = area[1].z; j<=area[1].w; j++) {
            vec3 src = texture(sTD2DInputs[0], vUV.st + vec2(i,j)/res).rgb;
            ave_B += src;
            var_B += src*src;
        }
    }
    ave_B /= val;
    var_B = abs(var_B/val - ave_B*ave_B);

    //C. lower left area
    vec3 ave_C = vec3(0.0);
    vec3 var_C = vec3(0.0);
    for(float i = area[2].x; i<=area[2].y; i++) {
        for(float j = area[2].z; j<=area[2].w; j++) {
            vec3 src = texture(sTD2DInputs[0], vUV.st + vec2(i,j)/res).rgb;
            ave_C += src;
            var_C += src*src;
        }
    }
    ave_C /= val;
    var_C = abs(var_C/val - ave_C*ave_C);

    //D. lower right area
    vec3 ave_D = vec3(0.0);
    vec3 var_D = vec3(0.0);
    for(float i = area[3].x; i<=area[3].y; i++) {
        for(float j = area[3].z; j<=area[3].w; j++) {
            vec3 src = texture(sTD2DInputs[0], vUV.st + vec2(i,j)/res).rgb;
            ave_D += src;
            var_D += src*src;
        }
    }
    ave_D /= val;
    var_D = abs(var_D/val - ave_D*ave_D);

    vec4 color;
    float sigma = 1e+2;
    float sigma_A = var_A.r + var_A.g + var_A.b;
    if (sigma_A < sigma) {
        sigma = sigma_A;
        color = vec4(ave_A, 1.0);
    }

    float sigma_B = var_B.r + var_B.g + var_B.b;
    if (sigma_B < sigma) {
        sigma = sigma_B;
        color = vec4(ave_B, 1.0);
    }

    float sigma_C = var_C.r + var_C.g + var_C.b;
    if (sigma_C < sigma) {
        sigma = sigma_C;
        color = vec4(ave_C, 1.0);
    }
    float sigma_D = var_D.r + var_D.g + var_D.b;
    if (sigma_D < sigma) {
        sigma = sigma_D;
        color = vec4(ave_D, 1.0);
    }

    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![KuwaharaFilter](https://user-images.githubusercontent.com/21966381/115665076-b0f4ba00-a37d-11eb-9742-7ff4c8edb4d5.jpg)

## Reference

https://qiita.com/Cartelet/items/5c1c012c132be3aa9608
