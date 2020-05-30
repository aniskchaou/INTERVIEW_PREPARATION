
# Decorator pattern
![enter image description here](https://www.tutorialspoint.com/design_pattern/images/decorator_pattern_uml_diagram.jpg)
_Decorator pattern_ allows a user to add new functionality to an existing object without altering its structure. This type of design _pattern_ comes under structural _pattern_ as this _pattern_ acts as a wrapper to existing class.


**Window.java**

    class Window{
        void draw()
        {
            System.out.println("draw window");
        }
    }

**IconWindow .java**

    class IconWindow extends Window{
    
        @Override
        void draw() {
            System.out.println("draw icon ");
            super.draw();
        }
     
    }


**ScrollBarWindow .java**

    class ScrollBarWindow extends Window
    {
    
        @Override
        void draw() {
            System.out.println("draw scrollbar ");
            super.draw();
        }
     
    }

**WindowDecorator .java**

    class WindowDecorator extends Window{
        
        Window window;
    
        public WindowDecorator(Window window) {
            this.window = window;
        }
    
        @Override
        void draw() {
           window.draw();
        }
        
        
        
    }

**IconWindowDecorator .java**

    class IconWindowDecorator extends WindowDecorator{
        
        public IconWindowDecorator(Window window) {
            super(window);
        }
    
        @Override
        void draw() {
            System.out.println("draw icon");
            window.draw();
        }
        
        
    }

**ScrollBarWindowDecorator .java**

    class ScrollBarWindowDecorator extends WindowDecorator
    {
        
        public ScrollBarWindowDecorator(Window window) {
            super(window);
        }
    
        @Override
        void draw() {
            System.err.println("draw scrollbar");
            window.draw();
        }
        
        
        
    }

**Client.java**

    class Client{
        
        public static void main(String[] args) 
        {
                //we can't combine icon and scrollbar
            IconWindow iconWindow=new IconWindow();
            iconWindow.draw();
            
            ScrollBarWindow scrollBarWindow=new ScrollBarWindow();
           scrollBarWindow.draw();
            
            //with decorators
            Window window=new Window();
            IconWindowDecorator iconWindowDecorator=new IconWindowDecorator(window);
            ScrollBarWindowDecorator barWindowDecorator=new ScrollBarWindowDecorator(iconWindowDecorator);
            barWindowDecorator.draw();
            
        }
    }
