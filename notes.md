# 4.2 - Sending rays into the scene
At its core, a ray tracer sends rays through pixels and computes the color seen in the direction of those rays.

## Steps
1. calculate the ray from each "eye" through the pixel.
2. determine which objects the rays intersects, and 
3. computes a color for the closest intersection point.

## Virtual Viewpoints 
virual rectangle in the 3D world that contains the grid of image pixel locations. 

## Define the camera center 
point in 3d space from which all scene rays will origiate from. 
vector from the camera will be center to the Viewport and the camera center point to be the one unit. 
This distance is the focal point. 

## Linear Interpolation ( The Lerp )
gradient caused is the Lerp. Bread and butter of computer graphics for everything from colors to animations. 

$$blendedValue = (1 - a) \cdot startValue + a \cdot endValue$$

When $y = 1.0$ (top of the sky), $a = 1.0$, resulting in Blue $(0.5, 0.7, 1.0)$.When $y = -1.0$ (bottom), $a = 0.0$, resulting in White $(1.0, 1.0, 1.0)$.

# 5. Adding a Sphere 
## 5.1 - Ray-Sphere Intersection

Quadratic Formula 
Discriminant Value,Mathematical Result,Geometric Meaning
>0,"Two real solutions (t1​,t2​)",The ray enters and exits the sphere (two hits).
=0,One real solution (t),The ray is tangent to the sphere (grazing the edge).
<0,No real solutions,The ray misses the sphere entirely.

## 5.2 - Creating our first Raytraced image
Geometric Problem 
In Raytracing, represent a ray as a function of time. 

# 6 - Surface Normals and Multiple objects
## 6.1 - Shading with Surface Normals
Its a vector perpendicular to the surface at the point of intersection.
key design decision - whether normal vectors will have an arbitary length, or will be normalised to unit length.

Determines how light interacts with the object. 
Outward Normal calculated by taking the hit point ( P ) and subtracting the center of the sphere (C);

n = P - C

### Design choice: Unit length
all normal vectors will be unit length ( normalised ). 
Consistency - normalise at the start than to check if a vector is normalised everytime you use it in lighting equations. 
Efficency -  For certain shapes like spheres, you can get the unit normal without a square root simply by dividing the vector $(P - C)$ by the radius ($r$)

## 6.2 - Simplifieng the Ray-Sphere Intersection code


## 6.3 - An abstraction for hittable objects
Adding a hittable class - header file named hittable.h.

hittable abstract class will have a hit function that takes in a ray. 
Most ray tracers have found convenience in to add valid interval for hits 
tMIN to tMAX, so the hits only "counts" if tMIN < t < tMAX. 

# 7 - Moving the camera code into its own class 

