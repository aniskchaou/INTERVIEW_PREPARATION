# Proxy pattern

_Proxy pattern_ **is used when we need to create a wrapper to cover the main object's complexity from the client.**
![enter image description here](https://upload.wikimedia.org/wikipedia/commons/thumb/7/75/Proxy_pattern_diagram.svg/439px-Proxy_pattern_diagram.svg.png)
**AtmMachine .java**

    class AtmMachine implements GetAtmData{
     
        int cashInMachine=2000;
    
        @Override
        public int getCashMachine() {
           return cashInMachine;
        }
    
    
        public void setCashInMachine(int cashInMachine) {
            this.cashInMachine = cashInMachine;
        }
        
        
        
    }

**AtmProxy .java**

    class AtmProxy implements GetAtmData{
    
        @Override
        public int getCashMachine() {
            AtmMachine atm=new AtmMachine();
           return  atm.getCashMachine();
        }
        
    }

**AtmState.java**

    class AtmState{
        
    }

**GetAtmData.java**

    interface GetAtmData{
        public int getCashMachine();
    }

**Client.java**

    class Client{
    
        public static void main(String[] args) {
            GetAtmData proxy=new AtmProxy();
            System.out.println(proxy.getCashMachine());
            
        }
    }
