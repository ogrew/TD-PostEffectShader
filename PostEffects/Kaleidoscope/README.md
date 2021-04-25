# Kaleidoscope

## Properties
![Properties](https://user-images.githubusercontent.com/21966381/115987296-709c7280-a5ef-11eb-9311-7ffab563f8cf.jpg)

## Shader Code

```glsl
uniform float time;
uniform float scale;

out vec4 fragColor;

vec2 Kaleido(vec2 uv)
{
	float th = atan(uv.y, uv.x);
	float r = pow(length(uv), .97);


	float f = 3.141592 / 3.5;

	th = abs(mod(th + f/4.0, f) - f/2.0) / (1.0 + r);
	//th = sin(th * 6.283 / f);

	return vec2(cos(th), sin(th)) * r * scale;
}

vec2 transform(vec2 at) {
	vec2 uv;
	uv.x = at.x * cos(time) - at.y * sin(time) - .1 * sin(time);
	uv.y = at.x * sin(time) + at.y * cos(time) + .1 * cos(time);
	return uv;  
}

vec4 scene(vec2 at) {
    return texture(sTD2DInputs[0], transform(at) * 2.0);
}

void main()
{
    vec2 uv = vUV.st;
    uv.x = mix(-1.0, 1.0, vUV.s);
    uv.y = mix(-1.0, 1.0, vUV.t);
    uv.y *= uTD2DInfos[0].res.y / uTD2DInfos[0].res.x;
    vec4 color = scene(Kaleido(uv));
    fragColor = TDOutputSwizzle(color);
}
```

## Gallery

![Kaleidoscope](https://user-images.githubusercontent.com/21966381/115665834-c6b6af00-a37e-11eb-9b2c-a4f39870de70.gif)

## Reference

https://www.shadertoy.com/view/4sfGzs
