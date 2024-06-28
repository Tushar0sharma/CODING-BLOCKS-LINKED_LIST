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
        node a=new node(0);
        node l=a;
        for(int i=0;i<n;i++){
            a.next=new node(sc.nextInt());
            a=a.next;
        }
        l=l.next;
        node t=solution(l);
        while(t!=null){
            System.out.print(t.val+" ");
            t=t.next;
        }
    }
    public static node solution(node head){
        node even=new node(0);
        node odd=new node(0);
        node l1=even;
        node l2=odd;
        boolean isodd=true;
        while(head!=null){
            if(!isodd){
                even.next=new node(head.val);
                even=even.next;
            }
            else{
                odd.next=new node(head.val);
                odd=odd.next;
            }
            isodd=!isodd;
            head=head.next;
        }
        odd.next=l1.next;
        even.next=null;
        return l2.next;
    }
}
```
