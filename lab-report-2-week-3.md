# This is my code for searchEngine

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


# Terminal Commands
![image](terminal1.png)

First is using add method:

1. add method: add "banner"
![image](addBanner.png)
2. add method: add "banana"
![image](addBanana.png)
3. add method: add "hey"
![image](addHey.png)

Relevent variables:
- String[] s, this is used to store the value being added
- ArrayList<String> listOfStrings, this is used to store all of the values that have been added

Relevent methods:
- .getPath(), returns the path of current link
- .equals(), compares two string, return true if same, false if not same.
- .split(), used to split the query by "="
- .getQuery(), returns the query of the current path
- .get(), gets the variable at that index
- .add(), adding the string to the list
- new Handler().getList(), prints the list of strings out separated by commas



Then we use the query method:

4. query method: search "ban"
![image](searchBan.png)

Relevent variables:
- String[] s, used to store the values being searched
- ArrayList<String> listOfStrings, this is the list of strings that are all added
- int i, used in the for loop

Relevent methods:
- .getPath(), returns the path of current link
- .equals(), compares two string, return true if same, false if not same
- .split(), used to split the query by "="
- .getQuery(), returns the query of the current path
- .get(), gets the variable at that index
- .add(), adding the string to the list
- .size(), used so the for loop stops when all strings are checked
- .contains(), used to check if string contains what it is searching
- new Handler().getList(), prints the list of strings out separated by commas

