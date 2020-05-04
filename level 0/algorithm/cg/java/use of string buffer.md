       static String concat(String[] strings)
       {
           if(strings.length>0)
           {
               StringBuilder sb=new StringBuilder();
               for (String s : strings) {
               sb.append(s);
               }
               
             return sb.toString();
           }else
           {
               return "";
           }
           
       }
