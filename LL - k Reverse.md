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
		node a=new node(0);
		node temp=a;
		int n=sc.nextInt();
		int target=sc.nextInt();
		for(int i=0;i<n;i++){
			a.next=new node(sc.nextInt());
			a=a.next;
		}
		node t=reverse(temp.next,target);
		while(t!=null){
			System.out.print(t.val+" ");
			t=t.next;
		}
    }
	public static node reverse(node head,int target){
		int cnt=0;
		node curr=head;
		node prev=null;
		node next=null;
		while(cnt<target && curr!=null){
			next=curr.next;
			curr.next=prev;
			prev=curr;
			curr=next;
			cnt++;
		}

		if(next!=null){
			head.next=reverse(next,target);
		}
		return prev;

	}
}
```
