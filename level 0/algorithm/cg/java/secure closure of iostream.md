

## read file

    public static void main(String[] args) {
            InputStreamReader reader=null;
             try {
                FileInputStream inputStream = new FileInputStream("MyFile.txt");
                 reader = new InputStreamReader(inputStream, "UTF-16");
                int character;
     
                while ((character = reader.read()) != -1) {
                    System.out.print((char) character);
                }
                
     
            } catch (IOException e) {
                e.printStackTrace();
            }finally{
                 
                    try {
                        reader.close();
                    } catch (IOException ex) {
                        Logger.getLogger(A.class.getName()).log(Level.SEVERE, null, ex);
                    }
                    
            }
        }

## write file

    OutputStreamWriter outputStreamWriter = null;
        try {
            FileOutputStream outputStream = new FileOutputStream("MyFile.txt");
             outputStreamWriter = new OutputStreamWriter(outputStream, "UTF-16");
             
            outputStreamWriter.write("Xin chào");
            outputStreamWriter.write("Hẹn gặp lại!");
             
            
        } catch (IOException e) {
            e.printStackTrace();
        }finally{
            try {
                outputStreamWriter.close();
            } catch (IOException ex) {
                
            }
        }
