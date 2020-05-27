## ISP : The Interface Segregation Principle
states that no client should be forced to depend on methods it does not use.


## Bad

**IMultiFunctions.java**

    interface IMultiFunctions{
        void scan();
        void print();
        void fax();
    
    }

**XeroxWorkCenter .java**

    class XeroxWorkCenter implements IMultiFunctions
    {
    
        @Override
        public void scan() {
            
        }
    
        @Override
        public void print() {
            
        }
    
        @Override
        public void fax() {
          
        }
        
    }

**HPrinterScanner .java**

    class HPrinterScanner implements IMultiFunctions{
    
        @Override
        public void scan() {
           
        }
    
        @Override
        public void print() {
            
        }
    
        @Override
        public void fax() {
           
        }
        
    }

## Good
**IMultiFunctions.java**

    interface IMultiFunctions{
    
    }

**IPrint.java**

    interface IPrint{
        void print();
    }

**IScan.java**

    interface IScan{
         void scan();
    }

**IFax.java**

    interface IFax{
        void fax();
    }

**XeroxWorkCenter .java**

    class XeroxWorkCenter implements IPrint,IFax
    {
        @Override
        public void print() {
            
        }
    
        @Override
        public void fax() {
          
        }
     
    }

**HPrinterScanner .java**

    class HPrinterScanner implements IScan{
    
        @Override
        public void scan() {
           
        }
      
    }
