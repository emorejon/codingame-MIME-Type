import java.util.*;
import java.io.*;
import java.math.*;

/**
 * Auto-generated code below aims at helping you parse
 * the standard input according to the problem statement.
 **/
class Solution {

    public static void main(String args[]) {
        Scanner in = new Scanner(System.in);
        int N = in.nextInt(); // Number of elements which make up the association table.
        int Q = in.nextInt(); // Number Q of file names to be analyzed.
        Map<String, String> extMime = new HashMap<String, String>();
        
        for (int i = 0; i < N; i++) {
            String EXT = in.next(); // file extension
            String MT = in.next(); // MIME type.
            extMime.put(EXT.toLowerCase(), MT);
        }
        
        in.nextLine();
        String[] name = new String[Q];
        for (int i = 0; i < Q; i++) {
            String FNAME = in.nextLine().toLowerCase(); // One file name per line.
            name[i] = FNAME.toLowerCase();
        }
        
        
        /*This nested for-loop section iterates backwards no each file name until it finds a '.',
        if it does, then it creates a substring of that name starting from the character after the '.'.
        I do this to compare this substring to the file extension provided.
        The substring is saved in the i iteration of the array isThere[]/*/
        
        String isThere[] = new String[Q];
        String ext= "";
        for(int i = 0; i < Q; i++){
            for(int j = name[i].length() - 1; j >= 0; j--){
                if(name[i].charAt(j) == '.'){
                    for(int z = j; z < name[i].length() - 1; z++){
                        ext = ext + name[i].charAt(z+1);
                    }
                    isThere[i] = ext;
                    break;
                }
            }   
            ext = ""; 
        }
        /*For each iteration where there wasn't a '.', the array element is null, in order to not get
        a nullPointerException, I assigned those elements to empty Strings.*/
        
        for(int i = 0; i < Q; i++){
            if(isThere[i] == null){
                isThere[i] = "";
            }
        }
        
        /*If the i element on isThere[] matches the key on extMime<String, String> then the 
        value correspondant to that key is printed, if not, then "UNKNOWN" is printed.*/        
        
        for(int i = 0; i < Q; i++){
            if(extMime.containsKey(isThere[i])){
                System.out.println(extMime.get(isThere[i]));
            }
            else{
                System.out.println("UNKNOWN");
            };
        }
    }
}
