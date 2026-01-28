# 1. Graph Definitions
## Definition 1: Undirected simple graph G = <V,E>:
- V is the set of vertices (đỉnh)
- E is the set of edges (cạnh), connect by 2 unordered distinct V
- there is at most 1 E connecting 2 V
![[Pasted image 20260121101002.png]]

EG:
V = {Denver, Chicago, ...}
E = {(Denver, Chicago), (Chicago, Detroit), ...}

## Definition 2: Undirected Multigraph G = <V,E>:
 - V is the set of vertices (đỉnh)
- E is the set of edges (cạnh), connect by 2 unordered distinct V
- - there can be multiple E connecting 2 V

![[Pasted image 20260121102159.png]]
## Definition 3: Undirected pseudograph G = <V,E>:
- V is the set of vertices (đỉnh)
- E is the set of edges (cạnh), connect by 2 unordered V
- there can be multiple E connecting 2 V
![[Pasted image 20260121102711.png]]
# Definition 4: Directed Simple graph G = <V,E>:
- V is the set of vertices (đỉnh)
- E is the set of edges (cạnh), connect by 2 ordered distinct V
- there is at most 1 E connecting 2 V
![[Pasted image 20260121103144.png]]
## Definition 5: Directed Multigraph G = <V,E>:
 - V is the set of vertices (đỉnh)
- E is the set of edges (cạnh), connect by 2 ordered distinct V
- - there can be multiple E connecting 2 V
# 2. Basic term in Undirected Graphs
## Definition 1:
Hai đỉnh u và v của đồ thị vô hƣớng G =<V, E> đƣợc gọi là kề
nhau nếu (u,v) là cạnh thuộc đồ thị G. Nếu e =(u, v) là cạnh của đồ thị G thì ta nói cạnh
này liên thuộc với hai đỉnh u và v, hoặc ta nói cạnh e nối đỉnh u với đỉnh v, đồng thời các
đỉnh u và v sẽ đƣợc gọi là đỉnh đầu của cạnh (u,v).

## Definition 2:
Ta gọi bậc của đỉnh v trong đồ thị vô hƣớng là số cạnh liên thuộc
với nó và ký hiệu là deg(v).

## Định lí 1:
- 1 đồ thị vô hướng có m cạnh thì ta có công thức 2m = tổng(deg(v))
## Hệ quả. Trong đồ thị vô hƣớng G=<V, E>, số các đỉnh bậc lẻ là một số chẵn.

## 1.2.2. Đường đi, chu trình, đồ thị liên thông
### Định nghĩa 1. Đường đi độ dài n từ đỉnh u đến đỉnh v trên đồ thị vô hướng
G=<V,E> là dãy x0, x1, . . ., xn-1, xn , trong đó n là số nguyên dƣơng, x0=u, xn=v, (xi,
xi+1)
E, i =0, 1, 2, . . ., n-1.
Đường đi như trên còn có thể biểu diễn thành dãy các cạnh
(x0, x1), (x1,x2) , . . ., (xn-1, xn).
Đỉnh u là đỉnh đầu, đỉnh v là đỉnh cuối của đường đi. Đường đi có đỉnh đầu trùng
với đỉnh cuối (u=v) đƣợc gọi là chu trình. Đƣờng đi hay chu trình đƣợc gọi là đơn nếu
như không có cạnh nào lặp lại.

### Định nghĩa 2. Đồ thị vô hƣớng đƣợc gọi là liên thông nếu luôn tìm đƣợc đƣờng đi
giữa hai đỉnh bất kỳ của nó.
Trong trƣờng hợp đồ thị G=<V, E> không liên thông, ta có thể phân rã G thành
một số đồ thị con liên thông mà chúng đôi một không có đỉnh chung. Mỗi đồ thị con nhƣ
vậy đƣợc gọi là một thành phần liên thông của G. Nhƣ vậy, đồ thị liên thông khi và chỉ
khi số thành phần liên thông của nó là 1.
Đối với đồ thị vô hƣớng, đƣờng đi từ đỉnh u đến đỉnh v cũng giống nhƣ đƣờng đi
từ đỉnh v đến đỉnh u. Chính vì vậy, nếu tồn tại đỉnh uV sao cho u có đƣờng đi đến tất cả
các đỉnh còn lại của đồ thị thì ta kết luận đƣợc đồ thị là liên thông.
### Định nghĩa 3. Cạnh e thuộc E đƣợc gọi là cầu nếu loại bỏ e làm tăng thành phần liên
thông của đồ thị. Đỉnh uV đƣợc gọi là đỉnh trụ nếu loại bỏ u cùng với các cạnh nối với
u làm tăng thành phần liên thông của đồ thị.
## Đồ thị vòng:
Đồ thị được nối thành hình tròn
## Đồ thị bánh xe:
Đồ thị được nối tất cả các đỉnh với nhau
## Đồ thị 2 phía
