```java
class node{
    int val;
    node next;
    node(int val){
        this.val=val;
        this.next=null;
    }
    public static void main(String[] args) {
        int []arr={1,2,3,4,5,6,-1};
        int k=3;
        call(arr,k);
    }
    public static void call(int []arr,int k){
        node a=new node(0);
        node l=a;
        int i=0;
        while(arr[i]!=-1){
            a.next=new node(arr[i++]);
            a=a.next;
        }
        l=l.next;
        call1(l, k);
    }
    public static void call1(node l,int k){
        int cnt=0;
        node h=l;
        while(h!=null){
            cnt++;
            h=h.next;
        }
        h=l;
        int target=cnt-k;
        if(target==0){
            System.out.println(h.val);
        }
        else{
            for(int i=0;i<target;i++){
                h=h.next;
            }
            System.out.println(h.val);
        }
    }

}
```
