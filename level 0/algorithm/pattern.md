
## print the following pattern triangle
1.  public  class Pattern1
2.  {
3.  public  static  void main(String[] args)
4.  {
5.  int i,j,n=7;
6.  System.out.println("Right angle triangle");
7.  for(i=1;i<n;i++)
8.  {
9.  for(j=1;j<=i;j++)
10.  {
11.  System.out.print(" *");
12.  }
13.  System.out.println("");
14.  }
15.  }
16.  }
pattern 2
17.  public  class Pattern8
18.  {
19.  public  static  void main(String[] args)
20.  {
21.  int size = 0;
22.  Character c;
23.  System.out.println();
24.  size = 5;
25.  int i, j, k;
26.  for (i = 0; i < size + 1; i++) { for (j = size; j > i; j--) {
27.  System.out.print(" ");
28.  }
29.  for (k = 0; k < (2 * i - 1); k++) {
30.  System.out.print("*");
31.  }
32.  System.out.println();
33.  }
34.  }
35.  }
36. 
pattern 3
37.  public  class Pattern4
38.  {
39.  public  static  void main(String[] args)
40.  {
41.  int n = 5;
42.  for(int i = 0 ; i <= n ; i++)
43.  {
44.  for(int j = 0 ; j < i ; j++)
45.  {
46.  System.out.print(j+1);
47.  }
48.  System.out.println("");
49.  }
50.  }
51.  }
52. 
pattern 3

53.  public  class pattern13
54.  {
55.  public  static  void main(String[] args)
56.  {
57.  int n=1;
58.  for(int i=0;i<6;i++)
59.  {
60.  for(int j=1;j<i;j++)
61.  {
62.  System.out.print(" "+n);
63.  n++;
64.  }
65.  System.out.println("");
66.  }
67.  }
68.  }
69. 
patern 4
70.  public  class Pattern6
71.  {
72.  public  static  void main(String[] args)
73.  {
74.  int i ,j;
75.  int n = 6;
76.  for(i = n; i>0 ; i-- )
77.  {
78.  for(j = 0; j<i ; j++)
79.  {
80.  System.out.print("*");
81.  }
82.  System.out.println("");
83.  }
84.  }
85.  }
86. 
pattern 5
87.  public  class Pattern11
88.  {
89.  public  static  void main(String[] args)
90.  {
91.  int coe=1,rows = 6;
92.  for(int i = 0; i < rows; i++) {
93.  for(int space = 1; space < rows - i; ++space) {
94.  System.out.print(" ");
95.  }

96.  for(int j = 0; j <= i; j++) {
97.  if (j == 0 || i == 0)
98.  coe = 1;
99.  else
100.  coe = coe * (i - j + 1) / j;

101.  System.out.printf("%4d", coe);
102.  }
103.  System.out.println();
104.  }
105.  }
106.  }
pattern 6
107.  public  class Pattern7
108.  {
109.  public  static  void main(String[] args)
110.  { int i ,j;
111.  int n = 5;
112.  for(i = n; i>0 ; i-- )
113.  {
114.  for(j = 1; j<=i ; j++)
115.  {
116.  System.out.print(j);
117.  }
118.  System.out.println("");
119.  }
120.  }
121.  }
pattern 7
122.  public  class PatternBox
123.  {
124.  public  static  void main(String[] args) {
125.  for (int i = 1; i <= 10; i++)
126.  {
127.  for (int j = 1; j <= 10; j++)
128.  {
129.  if (i==1 || i==10 || j==1 || j==10 )
130.  System.out.print(" 1");
131.  else
132.  System.out.print(" ");
133.  }
134.  System.out.println();
135.  }
136.  }}
pattern 8
137.  public  class pattern{
138.  public  static  void main(String[] args){
139.  int lines=10;
140.  int i=1;
141.  int j;
142.  for(i=1;i<=lines;i++){// this loop is used to print the lines
143.  for(j=1;j<=i;j++){// this loop is used to print lines
144.  System.out.print(i*j+" ");
145.  }
146.  System.out.println("");
147.  }
148.  }
149.  }
pattern 9
1.  public  class Main{
2.  public  static  void main(String []args){
3.  int i,j,lines=5;
4.  for(i=1;i<=lines;i++){// this loop is used to print the lines
5.  for(j=lines;j>=1;j--){// this loop is used to print numbers in a line
6.  if(j!=i)
7.  System.out.print(j);
8.  else
9.  System.out.print("*");
10.  }
11.  System.out.println("");
12.  }
13.  }
14.  }    
