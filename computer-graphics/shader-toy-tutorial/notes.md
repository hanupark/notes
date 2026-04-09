
### [episode 2](https://www.youtube.com/watch?v=GgGBR4z8C9o)

```js
// lesson 2 code snippet, continuing 1

float Circle(vec2 uv, vec2 p, float r, float blur) {
    
    //The circle is **drawn wherever the distance is zero**, i.e., `length(uv - p) = 0`.
    float d = length(uv-p);
    float c = smoothstep(r, r-blur, d);
    
    return c;
}

void mainImage( out vec4 fragColor, in vec2 fragCoord )
{

    vec2 uv = fragCoord.xy/iResolution.xy;
    uv -= .5;
    uv.x *= iResolution.x/iResolution.y;
    
    float c = Circle(uv, vec2(.2, -.1), .4, .05);
    c += Circle(uv, vec2(-.5, .2), .1, .01);
    
    fragColor = vec4(vec3(c),1.0); 
    
}

```
---

### [episode 1](https://www.youtube.com/watch?v=u5HAYVHsasc)

what is a shader? basically a program that takes some input and outputs only a pixel color. 

ShaderToy  

```js

// lesson 1 code snippet

// the out vec4 fragColor is the color returned for any vec2 fraCoord coordinate that goes in
void mainImage( out vec4 fragColor, in vec2 fragCoord )
{

	// current pixel xy position / the canvas width height xy
	// this returns a normalized position of the pixel from [0,1)
	// the bottom left corner is 0,0 and goes out from there
    vec2 uv = fragCoord.xy/iResolution.xy;
    
    // subtract .5 from each vec2 such that the range is [-.5,.5)
    // shifts the coordinate system so the bottom left corner is -.5,-.5
    // the center is now 0,0
    uv -= .5;
    
    // multiply the x by a stretch factor that normalizes x [0,1) to y [0,1)
    // isotropic coordinates
    uv.x *= iResolution.x/iResolution.y;
    
    // how long the pixel is from the origin (0,0)
    // sqrt(uv.x^2 + uv.y^2)
    float d = length(uv);

    float r = 0.3;
    
    //smoothstep(A, B, X) returns a value between 0 and 1
    // x <= A return 0, x >= B return 1.
    // A to B goes from 0 to 1 as X increases.
    // when A <= X <= B smoothly interpolate.
    // when wanting 1 to 0, flip A and B.
    float c = smoothstep(r, r-.01, d);
    
    // return the colors gotten from the smoothstep
    fragColor = vec4(vec3(c),1.0); 
    
}
```
