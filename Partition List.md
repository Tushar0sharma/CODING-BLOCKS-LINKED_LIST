```java
import java.util.*;
class node{
    int val;
    node next;
    node(int val){
        this.val=val;
        this.next=null;
    }
}
public class Main {
    public static void main (String args[]) {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        int target=sc.nextInt();
        node a=new node(0);
        node l=a;
        for(int i=0;i<n;i++){
            a.next=new node(sc.nextInt());
            a=a.next;
        }
        l=l.next;
        node left=new node(0);
        node right=new node(0);
        node l1=left;
        node l2=right;
        while(l!=null){
            if(l.val<target){
                left.next=new node(l.val);
                left=left.next;
            }
            else{
                right.next=new node(l.val);
                right=right.next;
            }
            l=l.next;
        }
        right.next=null;
        left.next=l2.next;
        l1=l1.next;
        while(l1!=null){
            System.out.print(l1.val+" ");
            l1=l1.next;
        }
    }
}
```
