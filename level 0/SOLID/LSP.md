## LSP : The Liskov Substitution Principle
Objects should be replaceable by their subtypes

## Bad
**Product.java**

    public class Product{
        protected double discount=20;
        
        public double getDiscount()
        {
            return discount;
        }
    }

**InHouseProduct .java**

    public class  InHouseProduct extends Product{
    
        void applyExtraDiscount()
        {
            discount= (discount*1.5);
        }
    
    }

**ProductUtils.java**

    public class ProductUtils
    {
        public static void main(String[] args) {
            Product product1=new Product();
            Product product2=new Product();
            Product product3=new InHouseProduct();
            
            List<Product> productList=new ArrayList<Product>();
            productList.add(product1);
            productList.add(product2);
            productList.add(product3);
            
            for(Product product:productList)
            {
                    if(product instanceof Product)
                    ((InHouseProduct)product).applyExtraDiscount();
                    
                product.getDiscount();
            }
        }
    }

## Good
**Product.java**

    public class Product{
        protected double discount=20;
        
        public double getDiscount()
        {
            return discount;
        }
    }

**InHouseProduct .java**

    public class  InHouseProduct extends Product{
    
        @Override
        public double getDiscount() {
            this.applyExtraDiscount();
            return discount;
        }
    
        
        void applyExtraDiscount()
        {
            discount= (discount*1.5);
        }
    
    }

**ProductUtils.java**

    public class ProductUtils
    {
        public static void main(String[] args) {
            Product product1=new Product();
            Product product2=new Product();
            Product product3=new InHouseProduct();
            
            List<Product> productList=new ArrayList<Product>();
            productList.add(product1);
            productList.add(product2);
            productList.add(product3);
            
            for(Product product:productList)
            {  
                product.getDiscount();
            }
        }
    }
