# Maximum-frequency-in-HashMap
ackage HashMap;
import java.util.*;
public class MaxFrequency {
    public static void main(String[] args) {
        int [] arr={1,2,3,4,5,6,7,1,1,1};
        Map<Integer,Integer> freq=new HashMap<>();
        for(int el:arr ){ // harr ek element arr se travrse kro
            if(!freq.containsKey(el)){
                freq.put(el,1);
            } else{
                freq.put(el,freq.get(el)+1);
            }

        }
        System.out.println("frequency");
        System.out.println(freq.entrySet());
        int maxfre=0 ,anskey=-1;
        for(var e:freq.entrySet()){
            if(e.getValue()>maxfre){
                maxfre=e.getValue();
                anskey=e.getKey();

            }
        }
        for(var key : freq.keySet()){
            if(freq.get(key) > maxfre){
                maxfre= freq.get(key);
                anskey=key;
            }
        }
        System.out.printf("%d has max fre and it occurs %d times" ,anskey,maxfre);

    }
}
