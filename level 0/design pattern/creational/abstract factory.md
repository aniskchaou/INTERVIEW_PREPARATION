# Abstract Factory Pattern
![enter image description here](https://www-sop.inria.fr/axis/cbrtools/usermanual-eng/Icons/AbstractFactory.gif)
Provide an interface for creating families of related or dependent objects without specifying their concrete classes.

**Window.java**

    interface Window{
        
    }

**ScrollBar.java**

    interface ScrollBar
    {
        
    }

**WidgetFactory.java**

    interface WidgetFactory{
        ScrollBar createScrollBar();
        Window createWindow();
    }

**YellowThemeFactory.java**

    class YellowThemeFactory implements WidgetFactory{
    
        @Override
        public ScrollBar createScrollBar() {
            return new YellowThemeScrollBar();
        }
    
        @Override
        public Window createWindow() {
            return new YellowThemeWindow();
        }
        
    }

**PinkThemeFactory.java**

    class PinkThemeFactory implements WidgetFactory{
    
        @Override
        public ScrollBar createScrollBar() {
          return  new PinkThemeScrollBar();
        }
    
        @Override
        public Window createWindow() {
           return new PinkThemeWindow();
        }
        
    }

**YellowThemeScrollBar.java**

    class  YellowThemeScrollBar implements ScrollBar {
        
    }

**PinkThemeScrollBar.java**

    class PinkThemeScrollBar implements ScrollBar{
        
    }

**YellowThemeWindow.java**

    class YellowThemeWindow implements Window
    {
        
    }

**PinkThemeWindow.java**

    class PinkThemeWindow implements Window
    {
        
    }

**Client.java**

    class Client{
        
        static void initializeGui(Window window,ScrollBar scrollBar)
        {
            System.out.println(window.getClass().getName()+" "+scrollBar.getClass().getName());
        }
        
        public static void main(String[] args) {
            
            //
            Window window=new PinkThemeWindow();
            ScrollBar scrollBar=new YellowThemeScrollBar();
            initializeGui(window, scrollBar);
            
            WidgetFactory  factory=new PinkThemeFactory();
            factory.createWindow();
            factory.createWindow();
            
            factory=new YellowThemeFactory();
            factory.createScrollBar();
            factory.createWindow();
            
            
        }
    }
