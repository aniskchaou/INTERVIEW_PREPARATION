## find the longest repeating sequence in a string
**Input:**

str = "acbdfghybdf"

**Output:**

Longest repeating sequence: bdf

    1.  //Checks for the largest common prefix
    2.  public  static String lcp(String s, String t){
    3.  int n = Math.min(s.length(),t.length());
    4.  for(int i = 0; i < n; i++){
    5.  if(s.charAt(i) != t.charAt(i)){
    6.  return s.substring(0,i);
    7.  }
    8.  }
    9.  return s.substring(0,n);
    10.  }
    
    12.  public  static  void main(String[] args) {
    13.  String str = "acbdfghybdf";
    14.  String lrs="";
    15.  int n = str.length();
    16.  for(int i = 0; i < n; i++){
    17.  for(int j = i+1; j < n; j++){
    18.  //Checks for the largest common factors in every substring
    19.  String x = lcp(str.substring(i,n),str.substring(j,n));
    20.  //If the current prefix is greater than previous one
    21.  //then it takes the current one as longest repeating sequence
    22.  if(x.length() > lrs.length()) lrs=x;
    23.  }
    24.  }
    25.  System.out.println("Longest repeating sequence: "+lrs);
    26.  }
