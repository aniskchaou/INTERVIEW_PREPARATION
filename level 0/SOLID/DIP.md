## DIP : The Dependency Inversion Principle
Depend on abstractions, not on concretions

The principle states:

-   High-level modules should not depend on low-level modules.  **Both should depend on abstractions.**
-   Abstractions should not depend on details.  **Details should depend on abstractions.**

## Bad

**ProductCatalog.java**

    class ProductCatalog{
        SQLProductRepository  productRepository=new SQLProductRepository();
        List<String> products=productRepository.getAllProductNames();
    }

**SQLProductRepository.java**

    class SQLProductRepository{
        List<String> getAllProductNames(){
        return Arrays.asList("product 1","product 2");
       }
    }

## Good
**ProductCatalog.java**

    class ProductCatalog{
        ProductRepository  productRepository=ProductFactory.create();
        List<String> products=productRepository.getAllProductNames();
    }

**ProductRepository.java**

    interface ProductRepository{
         List<String> getAllProductNames();
    }

**SQLProductRepository .java**

    class SQLProductRepository implements ProductRepository{
        @Override
        public List<String> getAllProductNames(){
        return Arrays.asList("product 1","product 2");
       }
    }

**ProductFactory.java**

    class ProductFactory{
        static ProductRepository create(){
        return new SQLProductRepository();
    }
    }
