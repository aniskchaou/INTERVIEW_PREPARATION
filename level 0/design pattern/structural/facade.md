# Facade pattern
Facade pattern hides the complexities of the system and provides an interface to the client using which the client can access the system.
![enter image description here](https://upload.wikimedia.org/wikipedia/commons/a/ac/FacadeDesignPattern.png)

**InvoiceCustomerSystem.java**

    class InvoiceCustomerSystem{
        
        void createInvoiceForBill(Bill bill)
        {
            System.out.println("Create invoice for bill with amount "+bill.amount);
        }
    }

**BillingSystem.java**

    class BillingSystem{
        Bill createBill(int amount)
        {
            return new Bill(amount);
        }
    }
    
**Bill.java**

    class Bill{
        
        int amount;
    
        public Bill(int amount) {
            this.amount = amount;
        }
        
    }

**FinancialSystemFacade.java**

    class FinancialSystemFacade{
        BillingSystem billingSystem;
        InvoiceCustomerSystem invoiceCustomerSystem;
    
        public void setBillingSystem(BillingSystem billingSystem) {
            this.billingSystem = billingSystem;
        }
    
        public void setInvoiceCustomerSystem(InvoiceCustomerSystem invoiceCustomerSystem) {
            this.invoiceCustomerSystem = invoiceCustomerSystem;
        }
        
        void createInvoice(int amount)
        {
              Bill bill=this.billingSystem.createBill(amount);
            this.invoiceCustomerSystem.createInvoiceForBill(bill);
        }
    }

**Client.java**

    class Client{
        public static void main(String[] args) {
            
            //
            BillingSystem billing=new BillingSystem();
            InvoiceCustomerSystem invoice=new InvoiceCustomerSystem();
            Bill bill=billing.createBill(1000);
            invoice.createInvoiceForBill(bill);
            
            //improved
            FinancialSystemFacade financialSystemFacade=new FinancialSystemFacade();
            financialSystemFacade.setBillingSystem(new BillingSystem());
            financialSystemFacade.setInvoiceCustomerSystem(new InvoiceCustomerSystem());
            financialSystemFacade.createInvoice(10000);
        }
    }
