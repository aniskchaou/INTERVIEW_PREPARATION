# Prototype pattern
The prototype pattern is a creational design pattern in software development. It is used when the type of objects to create is determined by a prototypical instance, which is cloned to produce new objects.
![enter image description here](https://www.baeldung.com/wp-content/uploads/2019/10/Prototype-Pattern.png)

**Graphic.java**

    abstract class Graphic{
      public  abstract Graphic clone();
    }

**Video .java**

    class Video extends Graphic{
        String url;
        void setUrl(String url)
        {
            this.url=url;
        }
    
        @Override
        public Graphic clone() {
          Video clone=new Video();
          clone.setUrl(this.url);
          return clone;
        }
    }

**Image.java**

    class Image extends Graphic
    {
         String url;
        void setUrl(String url)
        {
            this.url=url;
        }
        
          @Override
        public Graphic clone() {
          Image clone=new Image();
          clone.setUrl(this.url);
          return clone;
        }
    }

**GraphicTools.java**

    class GraphicTools{
        Graphic protype;
    
        public GraphicTools(Graphic protype) {
            this.protype = protype;
        }
        
        
        Graphic create()
        {
            return protype.clone();
        }
    }

**Client.java**

    class Client{
        public static void main(String[] args) {
            Image image=new Image();
            image.setUrl("www.image.com");
            
            //clone protype
            GraphicTools tools=new GraphicTools(image);
            Graphic graphic=tools.create();
            
            
        }
    }
