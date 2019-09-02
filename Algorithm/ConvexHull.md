## Convex Hull ##

1. Smallest convex set containing all the points 
2. Smallest area convext polygon enclosing all the points

## Application ##

1. Find the shortest distance from a to b to avoid polygon obstacle
2. Find the points with largest Elucidean distance 

## Graham Scan ##

1. Choose point p with smallest y-coordinate
2. Sort points by polar angle with p
3. Consider points in order unless it creats a ccw turn. 

## Determine CCW ##

```
    class 2DPoint {
        float x;
        float y;
        
        2DPoint(float x, float y) {
            this.x = x;
            this.y = y;
        }
    }
    
    int isCCW(2DPoint a, 2DPoint b, 2DPoint c) {
        float area = (b.x - a.x) * (c.y - a.y) - (b.y - a.y) * (c.x - a.x);
        
        if (area > 0) {
            return 1;  //ccw
        } else if (area < 0) {
            return -1; //cw
        } else {
            return 0; // collinear
        }
    }

```

## Graham Implementation ##

```
    2DPoint[] p = new 2DPoint[n];
    Stack<2DPoint> hull = new Stack<>();
    
    Arrays.sort(p, BY_Y_ORDER);
    Arrays.sort(p, p[0], BY_POLAR_ANGLE);
    
    hull.push(p[0]);
    hull.push(p[1]);
    
    for (int i = 2; i < n; i++) {
        2DPoint top = hull.pop();
        while (isCCW(top, hull.peek(), p[i]) <= 0) {
            top = hull.pop();
        }
        hull.push(top);
        hull.push(p[i]);
    }
```




