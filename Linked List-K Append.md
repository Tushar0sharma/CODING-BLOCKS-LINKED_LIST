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
	static Scanner sc;
	public static node generatell(int n){
		node a=new node(0);
		node l=a;
		for(int i=0;i<n;i++){
			a.next=new node(sc.nextInt());
			a=a.next;
		}
		l=l.next;
		return l;
	}
	public static node find(int target,int n,node head){
		if(head==null || head.next==null) return head;
		if(target==n || target==0) return head;
		node sec=head;
		for(int i=0;i<n-target-1;i++){
			sec=sec.next;
		}
		node temp=sec.next;
		sec.next=null;
		sec=temp;
		while(sec.next!=null){
			sec=sec.next;
		}
		sec.next=head;
		return temp;
	}
	public static void print(node l){
		while(l!=null){
			System.out.print(l.val+" ");
			l=l.next;
		}
	}
    public static void main(String args[]) {
		sc=new Scanner (System.in);
		int n=sc.nextInt();
		node head=generatell(n);
		int target=sc.nextInt();
		node l=find(target%n,n,head);
		print(l);
		
    }
}
```
