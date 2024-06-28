```java
class node{
    node next;
    int val;
    node(int val){
        this.val=val;
        this.next=null;
    }
}
class _03cool{
    public static void main(String[] args) {
        int []arr1={1,2,3,0};
        int []arr2={1,2,3,6,7};
        node a=new node(0);
        node b=new node(0);
        node l1=a;
        node l2=b;
        for(int i:arr1){
            a.next=new node(i);
            a=a.next;
        }
        for(int i:arr2){
            b.next=new node(i);
            b=b.next;
        }
        l1=l1.next;
        l2=l2.next;
        l1=rev(l1);
        l2=rev(l2);

        int carry=0;
        node ans=new node(0);
        node l=ans;
        while(l1!=null && l2!=null){
            int sum=l1.val+l2.val+carry;
            carry=sum/10;
            ans.next=new node(sum%10);
            ans=ans.next;
            l1=l1.next;
            l2=l2.next;
        }
        while(l1!=null){
            int sum=l1.val+carry;
            carry=sum/10;
            ans.next=new node(sum%10);
            ans=ans.next;
            l1=l1.next;
        }
        while(l2!=null){
            int sum=l2.val+carry;
            carry=sum/10;
            ans.next=new node(sum%10);
            ans=ans.next;
            l2=l2.next;
        }
        if(carry!=0){
            ans.next=new node(carry);
        }
        l=l.next;
        l=rev(l);
        while(l!=null){
            System.out.print(l.val+" ");
            l=l.next;
        }
    }
    public static node rev(node l){
        node curr=l;
        node prev=null;
        while(curr!=null){
            node next=curr.next;
            curr.next=prev;
            prev=curr;
            curr=next;
        }
        return prev;
    }
}
```
