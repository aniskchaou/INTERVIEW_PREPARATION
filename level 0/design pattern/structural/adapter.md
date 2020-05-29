# Adapter Pattern
An Adapter pattern acts as a connector between two incompatible interfaces that otherwise cannot be connected directly.
![enter image description here](https://i.stack.imgur.com/1mPAh.gif)
**LegacyRectangle.java**

    class LegacyRectangle{
        int determineSize()
        {
            return 5;
        }
    }

**Rectangle.java**

    class Rectangle{
       int determineSize()
        {
            return 1;
        }
    }

**RectangleLegacyAdapter .java**

    class RectangleLegacyAdapter extends Rectangle{
        LegacyRectangle legacyRectangle;
    
        public RectangleLegacyAdapter(LegacyRectangle legacyRectangle) {
            this.legacyRectangle = legacyRectangle;
        }
    
        @Override
        int determineSize() {
           return this.legacyRectangle.determineSize();
        }
        
        
    }

**Client .java**

    class Client {
        
        public static void main(String[] args) {
            RectangleLegacyAdapter rectangleLegacyAdapter=new RectangleLegacyAdapter(new LegacyRectangle());
            calculateRectangleSize(rectangleLegacyAdapter);
        }
        
        static int calculateRectangleSize(Rectangle rectangle)
        {
            return rectangle.determineSize();
        }
    }
