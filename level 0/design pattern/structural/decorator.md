class Window{
    void draw()
    {
        System.out.println("draw window");
    }
}

class IconWindow extends Window{

    @Override
    void draw() {
        System.out.println("draw icon ");
        super.draw();
    }
 
}



class ScrollBarWindow extends Window
{

    @Override
    void draw() {
        System.out.println("draw scrollbar ");
        super.draw();
    }
 
}

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