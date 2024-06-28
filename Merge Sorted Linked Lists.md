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
		for(int i=0;i<n;i++){
			int one=sc.nextInt();
			node a=new node(0);
			node b=new node(0);
			node l1=a;
			node l2=b;
			for(int x=0;x<one;x++){
				a.next=new node(sc.nextInt());
				a=a.next;
			}
			int two=sc.nextInt();
			for(int x=0;x<two;x++){
				b.next=new node(sc.nextInt());
				b=b.next;
			}
			l1=l1.next;
			l2=l2.next;

			node dummy=new node(0);
			node tail=dummy;

			while(l1!=null && l2!=null){
				if(l1.val<l2.val){
					dummy.next=l1;
					dummy=dummy.next;
					l1=l1.next;
				}
				else{
					dummy.next=l2;
					l2=l2.next;
					dummy=dummy.next;
				}
			}
			dummy.next=l1!=null?l1:l2;

			tail=tail.next;
			while(tail!=null){
				System.out.print(tail.val+" ");
				tail=tail.next;
			}
			System.out.println();
		}
    }
}
```
