```java
class node {
    int val;
    node next;
    
    node(int val) {
        this.val = val;
        this.next = null;
    }
}

class _04cool {
    public static void main(String[] args) {
        int[] arr1 = {12, 6, 29};
        int[] arr2 = {23, 5, 8};
        int[] arr3 = {90, 20, 59};
        int target = 101;

        node l1 = createList(arr1);
        node l2 = createList(arr2);
        node l3 = createList(arr3);

        findTripletsWithSum(l1, l2, l3, target);
    }

    public static node createList(int[] arr) {
        node dummy = new node(0);
        node current = dummy;
        for (int val : arr) {
            current.next = new node(val);
            current = current.next;
        }
        return dummy.next;
    }

    public static void findTripletsWithSum(node l1, node l2, node l3, int target) {
        for (node a = l1; a != null; a = a.next) {
            for (node b = l2; b != null; b = b.next) {
                for (node c = l3; c != null; c = c.next) {
                    if (a.val + b.val + c.val == target) {
                        System.out.println(a.val + " + " + b.val + " + " + c.val + " = " + target);
                        return;
                    }
                }
            }
        }
    }
}
```
