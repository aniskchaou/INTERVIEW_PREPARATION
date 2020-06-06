## determine whether two strings are the anagram
**Input:**

    Two Strings are called the anagram if they contain the same characters. However, the order or sequence of the characters can be different.
    
    str1 = "Grab";
    str2 = "Brag";

**Output:**

    Both the strings are anagram.

**Program**

  
	static boolean hasSamelength(String str1, String str2) {
		return str1.length() != str2.length();
	}

	public static void main(String[] args) {
		String str1 = "Brag";
		String str2 = "Grab";

		// Converting both the string to lower case.
		str1 = str1.toLowerCase();
		str2 = str2.toLowerCase();

		// Checking for the length of strings
		if (hasSamelength(str1, str2)) {
			System.out.println("Both the strings are not anagram");
		} else {
			// Converting both the arrays to character array
			char[] string1 = str1.toCharArray();
			char[] string2 = str2.toCharArray();

			// Sorting the arrays using in-built function sort ()
			Arrays.sort(string1);
			Arrays.sort(string2);

			// Comparing both the arrays using in-built function equals ()
			if (Arrays.equals(string1, string2)) {
				System.out.println("Both the strings are anagram");
			} else {
				System.out.println("Both the strings are not anagram");
			}
		}
	}
