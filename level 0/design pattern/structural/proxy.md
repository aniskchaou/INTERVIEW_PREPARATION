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

class AtmProxy implements GetAtmData{

    @Override
    public int getCashMachine() {
        AtmMachine atm=new AtmMachine();
       return  atm.getCashMachine();
    }
    
}

class AtmState{
    
}

interface GetAtmData{
    public int getCashMachine();
}

class Client{

    public static void main(String[] args) {
        GetAtmData proxy=new AtmProxy();
        System.out.println(proxy.getCashMachine());
        
    }
}