# Các Mẫu Cấu trúc Dữ liệu & Giải thuật (Data Structures & Algorithms Patterns)

Các khuôn mẫu mã nguồn (code templates) cho khóa học [Data Structures and Algorithms Crash Course](https://leetcode.com/explore/interview/card/leetcodes-interview-crash-course-data-structures-and-algorithms/) từ LeetCode (có chỉnh sửa thêm từ tác giả).

### Sơ đồ luồng hỗ trợ (Helper Flowchart)

LƯU Ý: Đây là sơ đồ luồng hỗ trợ, bao quát được phần lớn các bài toán. Tuy nhiên, không thể bao quát được tất cả mọi bài toán có thể xảy ra.

![flowchart](https://github.com/Suryakant-Bharti/Important-Java-Concepts/assets/2780145/66a204d9-5e7d-484a-b04d-71ac2f1c2c86)

```kotlin
for(i in 1..<10) { print("$i ") }

val stack = Stack<Int>()  ;  stack.add(5)  ;  stack.removeAt(0)
stack.push(8)  ;  = stack.pop()  ;  = stack.peek()

val queue = ArrayDeque<Int>()  ;  queue.add(5)

var mutableList = mutableListOf("Mahipal","Nikhil","Rahul")
mutableList[0] = "Praveen"
mutableList.add("Abhi")
for(item in mutableList) { println(item) }

var mutableSet = mutableSetOf<Int>(6,10)
mutableSet.add(2)
for(item in mutableSet){ println(item) }
mutableSet.contains(str);  mutableSet.remove("B"); 

var mutableMap = mutableMapOf<Int,String>(1 to "Neha",2 to "Puja")
mutableMap.put(1,"Rani")
mutableMap.put(4,"Abhi")

for(value in mutableMap.values){ println(value) }
for(key in immutableMap.keys){ println(immutableMap[key]) }

map.put(100,"Amit");     map.remove(102);
map.containsKey(5);     map.containsValue("World");
```

```kotlin
fun main() {
    var myList = LinkedList()
    myList.addAtHead(99)
    myList.addAtHead("kkkk")
    println(myList.get(1))
}

class LinkedList {
    var head: Node? = null
    var tail: Node? = null
    var length: Int = 0
    inner class Node(var value: Any?){
        var next: Node? = null
    }

    fun addAtHead(value: Any?){
        val h = this.head
        val newNode = Node(value)
        newNode.next = this.head
        head = newNode
        if (h == null) tail = newNode
        this.length++
    }

    fun addAtTail(value: Any?){
        var h = head
        val newNode = Node(value)
        newNode.next = null
        while (h!!.next !=null) h = h.next
        h.next = newNode
        tail = newNode
        this.length++
    }

    fun addAtIndex(index: Int, value: Any?){
        var h = head
        var newNode = Node(value)
        var counter = 0
        if (index < 0 || index > this.length) return
        if (index == 0) {
            addAtHead(value)
            return
        }
        if (index == this.length) {
            addAtTail(value)
            return
        }
        while (counter != index-1){
            h = h!!.next
            counter++
        }
        newNode.next = h!!.next
        h.next = newNode
        this.length++
    }

    fun deleteAtIndex(index: Int) {
        var curr = this.head
        var prev:Node? = null
        var counter = 0
        if (index < 0 || index >= this.length) return
        if (index == 0){
            head = curr!!.next
            this.length--
            return
        }
        while (counter != index){
            prev = curr
            curr = prev!!.next
            counter++
        }
        prev!!.next = curr!!.next
        if (index == length-1) tail = prev
        this.length--
    }

    fun get(index: Int): Any?{
        var h = head
        var counter = 0
        if (index < 0 || index >= this.length) return -1
        while (counter != index){
            h = h!!.next
            counter++
        }
        return h!!.value
    }

}
```

```java
java.util.*

**Types:** Boolean char-Character Byte Short int-Integer Long Float Double

int[] ar = new int[5]; int ar[] = {3, 1, 9, 2};
int c[][]=new int[2][3]; int a[][]={{1,3,4},{3,4,5}};
**Array Class:** List<Integer> l1 = Arrays.asList(ar);
Arrays.sort(ar); Arrays.binarySearch(ar,9);

List<String> al = new ArrayList<String>();
int size = al.size(); al.add("Ravi");  al.remove(0);   //index

Set<String> hs = new HashSet<String>(); 
hs.add("A");  hs.contains(str);  hs.remove("B"); 
for (String val:hs) { println(val);}

Map<Integer,String> map = new HashMap<Integer,String>();  
map.put(100,"Amit");     map.remove(102);
map.containsKey(5);     map.containsValue("World");
for(Map.Entry m:map.entrySet()){  println(m.getKey()+" "+m.getValue())}  

Collections.max(al);  Collections.min(al);   Collections.sort(al)

length can be used for int[], double[], String[]

**String Class:** i length(), ch charAt(i ind), bo contains(chSeq s), 
bo equals(Obj another), sr replace(ch old, ch new), sr trim()
sr[] split(sr regex), i indexOf(i ch), toLowerCase() 

public class ListNode {
int val; ListNode next;
ListNode(int x) { val = x; }

public ListNode reverseList(ListNode head) {
     if(head == null || head.next == null)   return head;
     -ListNode newHead=reverseList(head.next);
     -head.next.next=head;  head.next=null;
     return newHead;}
```

### 1) Mảng - Hai con trỏ: một đầu vào, hai đầu đối lập (Array - Two pointers: one input, opposite ends)

```java
public int fn(int[] arr) {
    int left = 0;
    int right = arr.length - 1;
    int ans = 0;

    while (left < right) {
        // thực hiện một số logic xử lý ở đây với left và right
        if (CONDITION) {
            left++;
        } else {
            right--;
        }
    }

    return ans;
}
```

### 2) Mảng - Hai con trỏ: hai đầu vào, duyệt hết cả hai (Array - Two pointers: two inputs, exhaust both)

```java
public int fn(int[] arr1, int[] arr2) {
    int i = 0, j = 0, ans = 0;

    while (i < arr1.length && j < arr2.length) {
        // thực hiện một số logic xử lý ở đây
        if (CONDITION) {
            i++;
        } else {
            j++;
        }
    }

    while (i < arr1.length) {
        // thực hiện logic xử lý
        i++;
    }

    while (j < arr2.length) {
        // thực hiện logic xử lý
        j++;
    }

    return ans;
}
```

### 3) Mảng - Cửa sổ trượt (Array - Sliding window)

```java
public int fn(int[] arr) {
    int left = 0, ans = 0, curr = 0;

    for (int right = 0; right < arr.length; right++) {
        // thực hiện logic ở đây để thêm arr[right] vào curr

        while (WINDOW_CONDITION_BROKEN) {
            // loại bỏ arr[left] khỏi curr
            left++;
        }

        // cập nhật ans
    }

    return ans;
}
```

### 4) Mảng - Xây dựng mảng cộng dồn tiền tố (Array - Build a prefix sum)

```java
public int[] fn(int[] arr) {
    int[] prefix = new int[arr.length];
    prefix[0] = arr[0];

    for (int i = 1; i < arr.length; i++) {
        prefix[i] = prefix[i - 1] + arr[i];
    }

    return prefix;
}
```

### 5) Xây dựng chuỗi hiệu quả (Efficient string building)

```java
public String fn(char[] arr) {
    StringBuilder sb = new StringBuilder();
    for (char c: arr) {
        sb.append(c);
    }

    return sb.toString();
}
```

### 6) Tìm số lượng mảng con khớp với tiêu chí chính xác (Find number of subarrays that fit an exact criteria)

```java
public int fn(int[] arr, int k) {
    Map<Integer, Integer> counts = new HashMap<>();
    counts.put(0, 1);
    int ans = 0, curr = 0;

    for (int num: arr) {
        // thực hiện logic để thay đổi curr
        ans += counts.getOrDefault(curr - k, 0);
        counts.put(curr, counts.getOrDefault(curr, 0) + 1);
    }

    return ans;
}
```

### 7) Tìm kiếm nhị phân (Binary search)

```java
public int fn(int[] arr, int target) {
    int left = 0;
    int right = arr.length - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (arr[mid] == target) {
            // thực hiện xử lý
            return mid;
        }
        if (arr[mid] > target) {
            right = mid - 1;
        } else {
            left = mid + 1;
        }
    }

    // left là điểm chèn (insertion point)
    return left;
}
```

### 8) Ngăn xếp đơn điệu tăng dần (Monotonic increasing stack)

Logic tương tự có thể được áp dụng để duy trì một hàng đợi đơn điệu (monotonic queue).

```java
public int fn(int[] arr) {
    Stack<Integer> stack = new Stack<>();
    int ans = 0;

    for (int num: arr) {
        // đối với đơn điệu giảm dần, chỉ cần đổi dấu > thành <
        while (!stack.empty() && stack.peek() > num) {
            // thực hiện logic xử lý
            stack.pop();
        }

        stack.push(num);
    }

    return ans;
}
```

### 9) Tìm k phần tử lớn nhất/nhỏ nhất bằng Heap (Find top k elements with heap)

```java
public int[] fn(int[] arr, int k) {
    PriorityQueue<Integer> heap = new PriorityQueue<>(CRITERIA);
    for (int num: arr) {
        heap.add(num);
        if (heap.size() > k) {
            heap.remove();
        }
    }

    int[] ans = new int[k];
    for (int i = 0; i < k; i++) {
        ans[i] = heap.remove();
    }

    return ans;
}
```

### 10) Danh sách liên kết: con trỏ nhanh và chậm (Linked list: fast and slow pointer)

```java
public int fn(ListNode head) {
    ListNode slow = head;
    ListNode fast = head;
    int ans = 0;

    while (fast != null && fast.next != null) {
        // thực hiện logic xử lý
        slow = slow.next;
        fast = fast.next.next;
    }

    return ans;
}
```

### 11) Đảo ngược danh sách liên kết (Reversing a linked list)

```java
public ListNode fn(ListNode head) {
    ListNode curr = head;
    ListNode prev = null;
    while (curr != null) {
        ListNode nextNode = curr.next;
        curr.next = prev;
        prev = curr;
        curr = nextNode;
    }

    return prev;
}
```

### 12) Cây nhị phân: Tìm kiếm theo chiều sâu DFS - Đệ quy (Binary tree: DFS - recursive)

```java
public int dfs(TreeNode root) {
    if (root == null) {
        return 0;
    }

    int ans = 0;
    // thực hiện logic xử lý
    dfs(root.left);
    dfs(root.right);
    return ans;
}
```

### 13) Cây nhị phân: Tìm kiếm theo chiều sâu DFS - Lặp (Binary tree: DFS - iterative)

```java
public int dfs(TreeNode root) {
    Stack<TreeNode> stack = new Stack<>();
    stack.push(root);
    int ans = 0;

    while (!stack.empty()) {
        TreeNode node = stack.pop();
        // thực hiện logic xử lý
        if (node.left != null) {
            stack.push(node.left);
        }
        if (node.right != null) {
            stack.push(node.right);
        }
    }

    return ans;
}
```

### 14) Cây nhị phân: Tìm kiếm theo chiều rộng BFS - Lặp (Binary tree: BFS - iterative)

```java
public int fn(TreeNode root) {
    Queue<TreeNode> queue = new LinkedList<>();
    queue.add(root);
    int ans = 0;

    while (!queue.isEmpty()) {
        int currentLength = queue.size();
        // thực hiện logic xử lý cho cấp độ hiện tại (current level)

        for (int i = 0; i < currentLength; i++) {
            TreeNode node = queue.remove();
            // thực hiện logic xử lý
            if (node.left != null) {
                queue.add(node.left);
            }
            if (node.right != null) {
                queue.add(node.right);
            }
        }
    }

    return ans;
}
```

### 15) Đồ thị: DFS - Đệ quy (Graph: DFS - recursive)

Đối với các khuôn mẫu đồ thị, giả định rằng các đỉnh được đánh số từ 0 đến n - 1 và đồ thị được cho dưới dạng danh sách kề (adjacency list).

Tùy thuộc vào bài toán, bạn có thể cần chuyển đổi đầu vào thành một danh sách kề tương đương trước khi sử dụng các khuôn mẫu này.

```java
Set<Integer> seen = new HashSet<>();

public int fn(int[][] graph) {
    seen.add(START_NODE);
    return dfs(START_NODE, graph);
}

public int dfs(int node, int[][] graph) {
    int ans = 0;
    // thực hiện một số logic xử lý
    for (int neighbor: graph[node]) {
        if (!seen.contains(neighbor)) {
            seen.add(neighbor);
            ans += dfs(neighbor, graph);
        }
    }

    return ans;
}
```

### 16) Đồ thị: DFS - Lặp (Graph: DFS - iterative)

```java
public int fn(int[][] graph) {
    Stack<Integer> stack = new Stack<>();
    Set<Integer> seen = new HashSet<>();
    stack.push(START_NODE);
    seen.add(START_NODE);
    int ans = 0;

    while (!stack.empty()) {
        int node = stack.pop();
        // thực hiện một số logic xử lý
        for (int neighbor: graph[node]) {
            if (!seen.contains(neighbor)) {
                seen.add(neighbor);
                stack.push(neighbor);
            }
        }
    }

    return ans;
}
```

### 17) Đồ thị: BFS - Lặp (Graph: BFS - iterative)

```java
public int fn(int[][] graph) {
    Queue<Integer> queue = new LinkedList<>();
    Set<Integer> seen = new HashSet<>();
    queue.add(START_NODE);
    seen.add(START_NODE);
    int ans = 0;

    while (!queue.isEmpty()) {
        int node = queue.remove();
        // thực hiện một số logic xử lý
        for (int neighbor: graph[node]) {
            if (!seen.contains(neighbor)) {
                seen.add(neighbor);
                queue.add(neighbor);
            }
        }
    }

    return ans;
}
```

### 18) Tìm kiếm nhị phân: các phần tử trùng lặp, điểm chèn tận cùng bên trái (Binary search: duplicate elements, left-most insertion point)

```java
public int fn(int[] arr, int target) {
    int left = 0;
    int right = arr.length;
    while (left < right) {
        int mid = left + (right - left) / 2;
        if (arr[mid] >= target) {
            right = mid;
        } else {
            left = mid + 1;
        }
    }

    return left;
}
```

### 19) Tìm kiếm nhị phân: các phần tử trùng lặp, điểm chèn tận cùng bên phải (Binary search: duplicate elements, right-most insertion point)

```java
public int fn(int[] arr, int target) {
    int left = 0;
    int right = arr.length;
    while (left < right) {
        int mid = left + (right - left) / 2;
        if (arr[mid] > target) {
            right = mid;
        } else {
            left = mid + 1;
        }
    }

    return left;
}
```

### 20) Tìm kiếm nhị phân: cho các bài toán tham lam - tìm giá trị nhỏ nhất (Binary search: for greedy problems - looking for minimum)

```java
public int fn(int[] arr) {
    int left = MINIMUM_POSSIBLE_ANSWER;
    int right = MAXIMUM_POSSIBLE_ANSWER;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (check(mid)) {
            right = mid - 1;
        } else {
            left = mid + 1;
        }
    }

    return left;
}

public boolean check(int x) {
    // hàm này được triển khai tùy thuộc vào từng bài toán cụ thể
    return BOOLEAN;
}
```

### 21) Tìm kiếm nhị phân: cho các bài toán tham lam - tìm giá trị lớn nhất (Binary search: for greedy problems - looking for maximum)

```java
public int fn(int[] arr) {
    int left = MINIMUM_POSSIBLE_ANSWER;
    int right = MAXIMUM_POSSIBLE_ANSWER;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (check(mid)) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }

    return right;
}

public boolean check(int x) {
    // hàm này được triển khai tùy thuộc vào từng bài toán cụ thể
    return BOOLEAN;
}
```

### 22) Các bài toán Quay lui (Backtracking problems)

```java
public int backtrack(STATE curr, OTHER_ARGUMENTS...) {
    if (BASE_CASE) {
        // sửa đổi kết quả
        return 0;
    }

    int ans = 0;
    for (ITERATE_OVER_INPUT) {
        // sửa đổi trạng thái hiện tại (state)
        ans += backtrack(curr, OTHER_ARGUMENTS...)
        // hoàn tác việc sửa đổi trạng thái hiện tại
    }
}
```

### 23) Quy hoạch động: Ghi nhớ từ trên xuống (Dynamic programming: top-down memoization)

```java
Map<STATE, Integer> memo = new HashMap<>();

public int fn(int[] arr) {
    return dp(STATE_FOR_WHOLE_INPUT, arr);
}

public int dp(STATE, int[] arr) {
    if (BASE_CASE) {
        return 0;
    }

    if (memo.contains(STATE)) {
        return memo.get(STATE);
    }

    int ans = RECURRENCE_RELATION(STATE);
    memo.put(STATE, ans);
    return ans;
}
```

### 24) Xây dựng cây tiền tố Trie (Build a trie)

```java
// lưu ý: việc sử dụng một class chỉ thực sự cần thiết nếu bạn muốn lưu trữ dữ liệu tại mỗi nút (node).
// nếu không, bạn có thể triển khai một cây trie chỉ bằng cách sử dụng các hash map.
class TrieNode {
    // bạn có thể lưu trữ dữ liệu tại các nút nếu muốn
    int data;
    Map<Character, TrieNode> children;
    TrieNode() {
        this.children = new HashMap<>();
    }
}

public TrieNode buildTrie(String[] words) {
    TrieNode root = new TrieNode();
    for (String word: words) {
        TrieNode curr = root;
        for (char c: word.toCharArray()) {
            if (!curr.children.containsKey(c)) {
                curr.children.put(c, new TrieNode());
            }

            curr = curr.children.get(c);
        }

        // tại thời điểm này, bạn đã có một từ đầy đủ tại curr
        // bạn có thể thực hiện thêm logic xử lý ở đây để gán một thuộc tính cho curr nếu muốn
    }

    return root;
}
```

### 25) Giải thuật Dijkstra (Dijkstra's algorithm)

```java
int[] distances = new int[n];
Arrays.fill(distances, Integer.MAX_VALUE);
distances[source] = 0;

Queue<Pair<Integer, Integer>> heap = new PriorityQueue<Pair<Integer,Integer>>(Comparator.comparing(Pair::getKey));
heap.add(new Pair(0, source));

while (!heap.isEmpty()) {
    Pair<Integer, Integer> curr = heap.remove();
    int currDist = curr.getKey();
    int node = curr.getValue();
    
    if (currDist > distances[node]) {
        continue;
    }
    
    for (Pair<Integer, Integer> edge: graph.get(node)) {
        int nei = edge.getKey();
        int weight = edge.getValue();
        int dist = currDist + weight;
        
        if (dist < distances[nei]) {
            distances[nei] = dist;
            heap.add(new Pair(dist, nei));
        }
    }
}
```
