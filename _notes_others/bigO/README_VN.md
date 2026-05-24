# Bảng tra cứu Độ phức tạp Thời gian (Big-O) / Time Complexity (Big-O) Cheatsheet

Các ký hiệu Big O, Big Theta và Big Omega diễn đạt độ phức tạp về thời gian (time complexity) và không gian (space complexity) của một thuật toán. Chúng giúp chúng ta định lượng (quantify) hiệu quả (efficiency) của mã nguồn (code).

- **Big O:** Hiệu suất trường hợp xấu nhất (Worst-case performance) của một thuật toán.
- **Big Theta (Θ):** Hiệu suất trung bình (Average performance) của một thuật toán.
- **Big Omega (Ω):** Hiệu suất trường hợp tốt nhất (Best-case performance) của một thuật toán.

## Các Cấu trúc Dữ liệu Phổ biến (Common Data Structures)

![common datastructures](https://github.com/Suryakant-Bharti/Important-Java-Concepts/assets/2780145/fd776e01-1887-4c50-bc3f-6712d29eec0a)

## Các Thuật toán Sắp xếp (Sorting Algorithms)

![sorting_algorithms](https://github.com/Suryakant-Bharti/Important-Java-Concepts/assets/2780145/d8d54a3e-55de-4321-afc1-eda8f01aea60)

## Các Thuật toán Khác (Others Algorithms)

**Tìm kiếm Tuyến tính (Linear Search)** - O(n)

**Tìm kiếm Nhị phân (Binary Search)** - O(logn)

**Tập hợp (Set)** - Thêm/Xóa/Tìm kiếm (Add/remove/search): O(1)

**Vun đống (Heap)** (luôn cân bằng):
- thêm/xóa (add/delete): O(logn)
- tìm kiếm (search): O(n)
- tìm min/max: O(1)

**Quy hoạch Động (Dynamic Programming)** :
- Độ phức tạp Không gian (Space Complexity): O(n)
- Độ phức tạp Thời gian (Time Complexity): O(n.k), k là lượng công việc thực hiện ở mỗi bước

**Đệ quy (Recursion)** : hầu hết cũng đúng với Quay lui (Backtracking)
- nếu hàm tự gọi lại 2 lần: O(2^n)
- nếu hàm tự gọi lại 3 lần: O(3^n)

**Chia để trị (Divide and Conquer)**

**Tham lam (Greedy)**

## Kích thước đầu vào, Độ phức tạp & Dự đoán Thuật toán (Input size, Complexity & Algo guess)

- **n <= 10:** ```có thể là O(n^2.n!) hoặc O(4^n)``` - quay lui (backtracking) hoặc đệ quy vét cạn (brute-force recursive)
- **10 < n <= 20:** ```O(2^n)``` - quay lui (backtracking) và đệ quy (recursion)
- **20 < n <= 100:** ```O(n^3)``` - vòng lặp lồng nhau (nested loops)
- **100 < n <= 1,000:** ```O(n^2)``` - vòng lặp lồng nhau có tối ưu (nested loops with something efficient)
- **1,000 < n < 100,000:** ```O(n.logn) hoặc O(n)``` - hashmap, 2 con trỏ (2 pointers), cửa sổ trượt (sliding window), ngăn xếp đơn điệu (monotonic stack), tìm kiếm nhị phân (binary search), vun đống (heap)
- **100,000 < n < 1,000,000:** ```O(n) hoặc O(n.logn)``` với k nhỏ - có thể dùng hashmap hoặc tìm kiếm nhị phân
- **1,000,000 < n:** ```O(logn) hoặc O(1)``` - công thức toán học (math formula), tìm kiếm nhị phân hoặc hashmap
