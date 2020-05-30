## find all possible subsets of a string

**Input:**

    str = "ABC"

**Output:**

    All subsets for given string are:
    A
    AB
    ABC
    B
    BC
    C

**program**
 ```   
     public static void main(String[] args) {
	   String str = "ABC";
	   int start=0;
       int end = str.length();
       extractString(start, end, str);
  
  }
   
   static void extractString(int start,int end,String str)
   {
	   List<String> listSubsets=new ArrayList();
	   
	   
	   for (int i = start; i < end; i++) {
		for (int j = i; j < end; j++) {
			listSubsets.add(str.substring(i, j+1));
		  }
	    }
	  printAllSubsert(listSubsets);
   }
   
   static void printAllSubsert(List<String> listOfSubsets)
   {
	   for(String word:listOfSubsets)
	   {
		  System.out.println(word); 
	   }
   }
}
