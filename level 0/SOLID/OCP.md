## OCP : The Open Closed Principle

You should be able to extend a classes behavior, without modifying it.  **Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification.**

## Bad
**InsuranceCalculator.java**

    class InsuranceCalculator{
        
        int calculateDiscount(HealthInsuranceProfile customer )
        {
            if(customer.isLoyal())
              return 20;
            
         return 0;   
        }
    }
**HealthInsuranceProfile.java**

    class HealthInsuranceProfile{
        
        boolean isLoyal()
        {
            return true;
        }
        
    }

**VehiculeInsuranceProfile.java**

    class VehiculeInsuranceProfile{
            
            boolean isLoyal()
            {
                return true;
            }
            
     }

## Good
**InsuranceCalculator.java**

    class InsuranceCalculator{
        
        int calculateDiscount(CustomerProfile customer )
        {
            if(customer.isLoyal())
              return 20;
            
         return 0;   
        }
        
      
        
    }

**HealthInsuranceProfile .java**

    class HealthInsuranceProfile implements CustomerProfile {
        
        @Override
        public boolean isLoyal()
        {
            return true;
        }
        
    }

**VehiculeInsuranceProfile .java**

    class VehiculeInsuranceProfile implements CustomerProfile{
            
            @Override
            public boolean isLoyal()
            {
                return true;
            }
            
        }

**CustomerProfile.java**

    interface CustomerProfile
    {
        boolean isLoyal();
    }