

## Compare 2 strings 

 

       public static boolean compare(String x, String y){
           
            if(x.length()!=y.length())
                return false;
     
            for (int i = 0; i <x.length() ; i++) {
                if(x.charAt(i)!=y.charAt(i))
                    return false;
            }
            
            return true;
        }

    

## Frequence d'apparition

    public class FrequenceApparition {
    
        public static void main(String[] args) {
              String s = "sdfsd sdfsdf sdfsdf sdfs f ";
            String s1 = "sdfsd";
            int fre = 0;
           String[] array=s.split(" ");
            //algorithme
            for (int i = 0; i < array.length; i++) {
                if (s1.equals(array[i])) {
                    fre++;
                }
            }
            
            System.err.println("frequence :  " + fre);
    
        }
    }

## inverser une chaine


            String chaine = "hello world";
            char[] inputStringArray = chaine.toCharArray();
            String reverseString = "";
    
            for (int i = inputStringArray.length - 1; i >= 0; i--) {
                reverseString += inputStringArray[i];
            }
    
            System.err.println("" + reverseString);

## inverser une phrase


**algo**
 

     String chaine = "I love Java Programming"; 
            String[] temp = chaine.split(" ");
            String result = ""; 
      
    
            for (int i = 0; i < temp.length; i++) {
                
                if (i == temp.length - 1) 
                    result = temp[i] + result; 
                else
                    result = " " + temp[i] + result; 
            } 
            
            System.out.println(result);
    
## consonne voyelle


            char[] input = "hello world"
            char[] voyelle = "aeiouy".toCharArray();
            char[] consonne ="abcdfghjklmnpqrstvxz".toCharArray();
            int cons = 0;
            int voy = 0;
            
    
            //algorithme
            for (int i = 0; i < input.length; i++) {
                for (int j = 0; j < voyelle.length; j++) {
                    if (input[i] == voyelle[j]) {
                        voy++;
                    }
                }
    
                for (int j = 0; j < consonne.length; j++) {
                    if (input[i] == consonne[j]) {
                        cons++;
                    }
                }
    
            }
            
            System.err.println("consonne " + cons);
            System.err.println("voyelle " + voy);
    

## palindrome


    public static boolean isPalindrome(String s) {
        
                int i = 0;
                int j = s.length() - 1;
        
                while (i < j) {
                    if (s.charAt(i) != s.charAt(j)) {
                        return false;
                    }
        
                    i++;
                    j--;
                }
                return true;
            }

## UpperCase LowerCase



algo

    char maj[] = {'A', 'B', 'Z'};
    char min[] = {'a', 'b', 'z'};
    String input = "abz";
    char[] char_array = input.toCharArray();

    
    for (int k = 0; k < char_array.length; k++) {
        for (int l = 0; l < min.length; l++) {
            if (min[l] == char_array[k]) {
                char_array[k] = maj[l];
            }
        }
    }

    //affichage
    String res = new String(char_array);

## swap two string variables without using third or temp variable

    1.  public  static  void main(String[] args) {
    2.  String str1 = "Good", str2 = "morning";
    
    3.  System.out.println("Strings before swapping: " + str1 + " " + str2);
    
    4.  //Concatenate both the string str1 and str2 and store it in str1
    5.  str1 = str1 + str2;
    6.  //Extract str2 from updated str1
    7.  str2 = str1.substring(0, (str1.length() - str2.length()));
    8.  //Extract str1 from updated str1
    9.  str1 = str1.substring(str2.length());
    
    10.  System.out.println("Strings after swapping: " + str1 + " " + str2);
    11.  }
  
  ## separate the individual characters from a string

    1.  public  static  void main(String[] args) {
    2.  String string = "characters";
    
    4.  //Displays individual characters from given string
    5.  System.out.println("Individual characters from given string:");
    
    7.  //Iterate through the string and display individual character
    8.  for(int i = 0; i < string.length(); i++){
    9.  System.out.print(string.charAt(i) + " ");
    10.  }
    11.  }
## find the largest & smallest word in a string

    1.  public  static  void main(String[] args){
    2.  String string = "Hardships often prepare ordinary people for an extraordinary destiny";
    3.  String word = "", small = "", large="";
    4.  String[] words = new String[100];
    5.  int length = 0;
    
    7.  //Add extra space after string to get the last word in the given string
    8.  string = string + " ";
    
    10.  for(int i = 0; i < string.length(); i++){
    11.  //Split the string into words
    12.  if(string.charAt(i) != ' '){
    13.  word = word + string.charAt(i);
    14.  }
    15.  else{
    16.  //Add word to array words
    17.  words[length] = word;
    18.  //Increment length
    19.  length++;
    20.  //Make word an empty string
    21.  word = "";
    22.  }
    23.  }
    
    25.  //Initialize small and large with first word in the string
    26.  small = large = words[0];
    
    28.  //Determine smallest and largest word in the string
    29.  for(int k = 0; k < length; k++){
    
    31.  //If length of small is greater than any word present in the string
    32.  //Store value of word into small
    33.  if(small.length() > words[k].length())
    34.  small = words[k];
    
    36.  //If length of large is less than any word present in the string
    37.  //Store value of word into large
    38.  if(large.length() < words[k].length())
    39.  large = words[k];
    40.  }
    
    42.  System.out.println("Smallest word: " + small);
    43.  System.out.println("Largest word: " + large);
    44.  }
## find the frequency of characters

    1.  public  static  void main(String[] args) {
    2.  String str = "picture perfect";
    3.  int[] freq = new  int[str.length()];
    4.  int i, j;
    
    6.  //Converts given string into character array
    7.  char string[] = str.toCharArray();
    
    9.  for(i = 0; i <str.length(); i++) {
    10.  freq[i] = 1;
    11.  for(j = i+1; j <str.length(); j++) {
    12.  if(string[i] == string[j]) {
    13.  freq[i]++;
    
    15.  //Set string[j] to 0 to avoid printing visited character
    16.  string[j] = '0';
    17.  }
    18.  }
    19.  }
    
    21.  //Displays the each character and their corresponding frequency
    22.  System.out.println("Characters and their corresponding frequencies");
    23.  for(i = 0; i <freq.length; i++) {
    24.  if(string[i] != ' ' && string[i] != '0')
    25.  System.out.println(string[i] + "-" + freq[i]);
    26.  }
    27.  }
## find the duplicate words in a string

    1.  public  static  void main(String[] args) {
    2.  String string = "Big black bug bit a big black dog on his big black nose";
    3.  int count;
    
    5.  //Converts the string into lowercase
    6.  string = string.toLowerCase();
    
    8.  //Split the string into words using built-in function
    9.  String words[] = string.split(" ");
    
    11.  System.out.println("Duplicate words in a given string : ");
    12.  for(int i = 0; i < words.length; i++) {
    13.  count = 1;
    14.  for(int j = i+1; j < words.length; j++) {
    15.  if(words[i].equals(words[j])) {
    16.  count++;
    17.  //Set words[j] to 0 to avoid printing visited word
    18.  words[j] = "0";
    19.  }
    20.  }
    
    22.  //Displays the duplicate word if count is greater than 1
    23.  if(count > 1 && words[i] != "0")
    24.  System.out.println(words[i]);
    25.  }
    26.  }
## find reverse of a string

    1.  public  static  void main(String[] args) {
    2.  String string = "Dream big";
    3.  //Stores the reverse of given string
    4.  String reversedStr = "";
    
    6.  //Iterate through the string from last and add each character to variable reversedStr
    7.  for(int i = string.length()-1; i >= 0; i--){
    8.  reversedStr = reversedStr + string.charAt(i);
    9.  }
    
    11.  System.out.println("Original string: " + string);
    12.  //Displays the reverse of given string
    13.  System.out.println("Reverse of given string: " + reversedStr);
    14.  }
##  one string is a rotation of another

    1.  public  static  void main(String[] args) {
    2.  String str1 = "abcde", str2 = "deabc";
    
    4.  if(str1.length() != str2.length()){
    5.  System.out.println("Second string is not a rotation of first string");
    6.  }
    7.  else {
    8.  //Concatenate str1 with str1 and store it in str1
    9.  str1 = str1.concat(str1);
    
    11.  //Check whether str2 is present in str1
    12.  if(str1.indexOf(str2) != -1)
    13.  System.out.println("Second string is a rotation of first string");
    14.  else
    15.  System.out.println("Second string is not a rotation of first string");
    16.  }
    17.  }
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

    1.  public  static  void main(String[] args) {
    
    3.  String str = "ABC";
    4.  int len = str.length();
    5.  int temp = 0;
    6.  //Total possible subsets for string of size n is n*(n+1)/2
    7.  String arr[] = new String[len*(len+1)/2];
    
    9.  //This loop maintains the starting character
    10.  for(int i = 0; i < len; i++) {
    11.  //This loop adds the next character every iteration for the subset to form and add it to the array
    12.  for(int j = i; j < len; j++) {
    13.  arr[temp] = str.substring(i, j+1);
    14.  temp++;
    15.  }
    16.  }
    
    18.  //This loop prints all the subsets formed from the string.
    19.  System.out.println("All subsets for given string are: ");
    20.  for(int i = 0; i < arr.length; i++) {
    21.  System.out.println(arr[i]);
    22.  }
    23.  }

## remove all the white spaces from a string

**Input:**

str1 = "Remove white spaces"

**Output:**

    String after removing all the white spaces : Removewhitespaces
    
    1.  public  static  void main(String[] args) {
    
    3.  String str1="Remove white spaces";
    
    5.  //Removes the white spaces using regex
    6.  str1 = str1.replaceAll("\\s+", "");
    
    8.  System.out.println("String after removing all the white spaces : " + str1);
    9.  }
## find all the permutations of a string
**Input:**

char str[] = "ABC" 

**Output:**

All the permutations of the string are:
ABC
ACB
BAC
BCA
CBA
CAB

    1.  //Function for swapping the characters at position I with character at position j
    2.  public  static String swapString(String a, int i, int j) {
    3.  char[] b =a.toCharArray();
    4.  char ch;
    5.  ch = b[i];
    6.  b[i] = b[j];
    7.  b[j] = ch;
    8.  return String.valueOf(b);
    9.  }
    
    11.  public  static  void main(String[] args)
    12.  {
    13.  String str = "ABC";
    14.  int len = str.length();
    15.  System.out.println("All the permutations of the string are: ");
    16.  generatePermutation(str, 0, len);
    17.  }
    
    19.  //Function for generating different permutations of the string
    20.  public  static  void generatePermutation(String str, int start, int end)
    21.  {
    22.  //Prints the permutations
    23.  if (start == end-1)
    24.  System.out.println(str);
    25.  else
    26.  {
    27.  for (int i = start; i < end; i++)
    28.  {
    29.  //Swapping the string by fixing a character
    30.  str = swapString(str,start,i);
    31.  //Recursively calling function generatePermutation() for rest of the characters
    32.  generatePermutation(str,start+1,end);
    33.  //Backtracking and swapping the characters again.
    34.  str = swapString(str,start,i);
    35.  }
    36.  }
    37.  }
## to divide a string in 'N' equal parts.
**Input:**

str = "aaaabbbbcccc"

**Output:**

Equal parts of given string are
aaaa
bbbb
cccc

    1.  public  static  void main(String[] args) {
    2.  String str = "aaaabbbbcccc";
    
    4.  //Stores the length of the string
    5.  int len = str.length();
    6.  //n determines the variable that divide the string in 'n' equal parts
    7.  int n = 3;
    8.  int temp = 0, chars = len/n;
    9.  //Stores the array of string
    10.  String[] equalStr = new String [n];
    11.  //Check whether a string can be divided into n equal parts
    12.  if(len % n != 0) {
    13.  System.out.println("Sorry this string cannot be divided into "+ n +" equal parts.");
    14.  }
    15.  else {
    16.  for(int i = 0; i < len; i = i+chars) {
    17.  //Dividing string in n equal part using substring()
    18.  String part = str.substring(i, i+chars);
    19.  equalStr[temp] = part;
    20.  temp++;
    21.  }
    22.  System.out.println(n + " equal parts of given string are ");
    23.  for(int i = 0; i < equalStr.length; i++) {
    24.  System.out.println(equalStr[i]);
    25.  }
    26.  }
    27.  }

## determine whether two strings are the anagram
**Input:**

Two Strings are called the anagram if they contain the same characters. However, the order or sequence of the characters can be different.

str1 = "Grab";
str2 = "Brag";

**Output:**

Both the strings are anagram.

    1.  public  static  void main (String [] args) {
    2.  String str1="Brag";
    3.  String str2="Grab";
    
    5.  //Converting both the string to lower case.
    6.  str1 = str1.toLowerCase();
    7.  str2 = str2.toLowerCase();
    
    9.  //Checking for the length of strings
    10.  if (str1.length() != str2.length()) {
    11.  System.out.println("Both the strings are not anagram");
    12.  }
    13.  else {
    14.  //Converting both the arrays to character array
    15.  char[] string1 = str1.toCharArray();
    16.  char[] string2 = str2.toCharArray();
    
    18.  //Sorting the arrays using in-built function sort ()
    19.  Arrays.sort(string1);
    20.  Arrays.sort(string2);
    
    22.  //Comparing both the arrays using in-built function equals ()
    23.  if(Arrays.equals(string1, string2) == true) {
    24.  System.out.println("Both the strings are anagram");
    25.  }
    26.  else {
    27.  System.out.println("Both the strings are not anagram");
    28.  }
    29.  }
    30.  }
## Headingcount the total number of punctuation characters exists in a string

**Input:**

char str [] = "Good Morning! Mr. James Potter. Had your breakfast?"

**Output:**

If any character in the string is matched with ('!', "," ,"\'" ,";" ,"\"", ".", "-" ,"?"), increment the count by 1.

Total number of punctuation characters exists in string: 4

    1.  public  static  void main (String [] args) {
    2.  //Stores the count of punctuation marks
    3.  int countPuncMarks = 0;
    4.  String str = "Good Morning! Mr. James Potter. Had your breakfast?";
    5.  for (int i = 0; i < str.length(); i++) {
    6.  //Checks whether given character is punctuation mark
    7.  if(str.charAt(i) == '!' || str.charAt(i) == ',' || str.charAt(i) == ';' || str.charAt(i) == '.' || str.charAt(i) == '?' || str.charAt(i) == '-' ||
    8.  str.charAt(i) == '\'' || str.charAt(i) == '\"' || str.charAt(i) == ':') {
    9.  countPuncMarks++;
    10.  }
    11.  }
    12.  System.out.println("Total number of punctuation characters exists in string: " + countPuncMarks);
    13.  }