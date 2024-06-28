---java
class node{
    int val;
    node next;
    node(int val){
        this.val=val;
        this.next=null;
    }
    node(int val,node next){
        this.val=val;
        this.next=next;
    }
}
public class _01cool {
    public static void main(String[] args) {
        node a=new node(0);
        node l=a;
        int []arr={1,2,2,2,2,3,4,5};
        for(int i:arr){
            a.next=new node(i);
            a=a.next;
        }
        l=l.next;
        check(l);
    }
    public static void check(node l){
        node h=l;
        while(h!=null){
            if(h.val%2!=0){
                System.out.println(h.val);
            }
            h=h.next;
        }
        h=l;
        while(h!=null){
            if(h.val%2==0){
                System.out.println(h.val);
            }
            h=h.next;
        }
    }

}

---

