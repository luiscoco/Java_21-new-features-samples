# Java 21 Main features samples 


## 1. Pattern Matching for switch

This feature extends the capabilities of switch expressions and statements, allowing you to express more complex and sophisticated data pattern matching

```java
public static String describeShape(Object shape) {
    return switch (shape) {
        case Circle c    -> "Circle with radius " + c.getRadius();
        case Rectangle r -> "Rectangle with width " + r.getWidth() + " and height " + r.getHeight();
        case null        -> "It's null"; 
        default          -> "Some other shape"; 
    };
}
```

Pattern matching in switch can be combined with '**guards**' (additional boolean conditions) to refine matching criteria

```java
enum TrafficLight { RED, YELLOW, GREEN }

String handleMessage(TrafficLight light) {
    return switch (light) {
        case RED     -> "Stop!";
        case YELLOW  -> "Prepare to stop";
        case GREEN   -> "Go!";
        default      -> "Unknown signal"; // Should rarely happen
    };
}
```

Pattern matching offers powerful data extraction mechanisms in switch expressions and statements

```java
record Rectangle(int width, int height) {}
record Circle(int radius) {}
record Triangle(int base, int height) {}

String calculateArea(Shape shape) {
    return switch (shape) {
        case Rectangle(int w, int h) -> "Rectangle area: " + (w * h);
        case Circle(int r)           -> "Circle area: " + (Math.PI * r * r);
        case Triangle(int b, int h)  -> "Triangle area: " + (0.5 * b * h);
        default                      -> "Unsupported shape";
    };
}
```

```java

```





