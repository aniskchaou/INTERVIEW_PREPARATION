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
    




