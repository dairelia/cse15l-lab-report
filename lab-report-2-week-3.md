This is my code for searchEngine

    class Handler implements URLHandler {
    
        int num = 0;
        ArrayList<String> listOfString = new ArrayList<String> ();

        public String getList(ArrayList<String> someList){
        
            if(someList.size() == 0){
                return "empty list";
            }
            String temp = someList.get(0);
            for(int i = 1; i < someList.size(); i++){
                temp = temp + ", " + someList.get(i);
            }
            return temp; 
        }
        public String handleRequest(URI url) {
            if (url.getPath().equals("/")) {
                if(listOfString.size()!= 0){
                    return new Handler().getList(listOfString);
                }
                return "empty list";
            } 

            else if (url.getPath().equals("/add")) {
                String[] s = url.getQuery().split("=");
                if(s[0].equals("s")){
                    listOfString.add(s[1]);
                    return s[1] + " added, now the list is " + new Handler().getList(listOfString);
                }
                return new Handler().getList(listOfString);
            } 

            else if (url.getPath().equals("/search")) {
                String[] s = url.getQuery().split("=");
                ArrayList<String> searchList = new ArrayList<String>();
                if(s[0].equals("s")){
                    for(int i = 0; i < listOfString.size(); i++){
                        if(listOfString.get(i).contains(s[1])){
                            searchList.add(listOfString.get(i));
                        }
                    }
                    return new Handler().getList(searchList);
                }
            else{
                return "Query not found";
            }

            } 

            else {
                return "404 Not Found!";
            }
        }
    }
