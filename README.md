<h1 id="1-struktur-pohon">1. Struktur Pohon</h1>
<ul>
<li>Pre Order 	: <a href="https://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/">https://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/</a></li>
<li>In Order	: <a href="https://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/">https://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/</a></li>
<li>Post Order	: <a href="https://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/">https://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/</a></li>
</ul>
<h1 id="2-source-code">2. Source Code</h1>
<h3>Pre Order</h3>

<ul>
<li>Source Code</li>
</ul>
<pre><code class="language-c++">// C++ program for different tree traversals
#include &lt;bits/stdc++.h&gt;
using namespace std;
 
// A binary tree node has data, pointer to left child
// and a pointer to right child
struct Node {
    int data;
    struct Node *left, *right;
};
 
// Utility function to create a new tree node
Node* newNode(int data)
{
    Node* temp = new Node;
    temp-&gt;data = data;
    temp-&gt;left = temp-&gt;right = NULL;
    return temp;
}
 
// Given a binary tree, print its nodes in preorder
void printPreorder(struct Node* node)
{
    if (node == NULL)
        return;
 
    // First print data of node
    cout &lt;&lt; node-&gt;data &lt;&lt; &quot; &quot;;
 
    // Then recur on left subtree
    printPreorder(node-&gt;left);
 
    // Now recur on right subtree
    printPreorder(node-&gt;right);
}
 
// Driver code
int main()
{
    struct Node* root = newNode(1);
    root-&gt;left = newNode(2);
    root-&gt;right = newNode(3);
    root-&gt;left-&gt;left = newNode(4);
    root-&gt;left-&gt;right = newNode(5);
 
    // Function call
    cout &lt;&lt; &quot;Preorder traversal of binary tree is \n&quot;;
    printPreorder(root);
 
    return 0;
}
</code></pre>
<ul>
<li>Penjelasan</li>
</ul>
<pre><code class="language-c++">struct Node {
  int data;
  struct Node *left, *right;
};
</code></pre>
<p>  Di sini, Node adalah struktur yang merepresentasikan simpul atau node dalam pohon biner. Setiap simpul memiliki data (variabel data), serta pointer ke simpul anak kiri (left) dan anak kanan (right).</p>
<pre><code class="language-c++">Node* newNode(int data)
{
  Node* temp = new Node;
  temp-&gt;data = data;
  temp-&gt;left = temp-&gt;right = NULL;
  return temp;
}

</code></pre>
<p>Fungsi newNode digunakan untuk membuat simpul baru dengan data tertentu. Fungsi ini mengalokasikan memori untuk simpul baru, mengatur nilai data, serta menginisialisasi pointer anak kiri dan anak kanan menjadi NULL.</p>
<pre><code class="language-c++">
void printPreorder(struct Node* node)
{
    if (node == NULL)
        return;

    // First print data of node
    cout &lt;&lt; node-&gt;data &lt;&lt; &quot; &quot;;

    // Then recur on left subtree
    printPreorder(node-&gt;left);

    // Now recur on right subtree
    printPreorder(node-&gt;right);
}
</code></pre>
<p>Fungsi printPreorder adalah implementasi dari penelusuran pohon dengan metode preorder. Prosesnya adalah sebagai berikut:</p>
<ul>
<li>Cetak data dari simpul saat ini.</li>
<li>Rekursif panggil printPreorder untuk anak kiri simpul saat ini.</li>
<li>Rekursif panggil printPreorder untuk anak kanan simpul saat ini.</li>
</ul>
<pre><code class="language-c++">
int main()
{
    struct Node* root = newNode(1);
    root-&gt;left = newNode(2);
    root-&gt;right = newNode(3);
    root-&gt;left-&gt;left = newNode(4);
    root-&gt;left-&gt;right = newNode(5);

    // Function call
    cout &lt;&lt; &quot;Preorder traversal of binary tree is \n&quot;;
    printPreorder(root);

    return 0;
}
</code></pre>
<p>Di dalam fungsi main, kita membuat pohon biner dengan beberapa simpul dan menyimpan alamat akar pohon pada variabel root. Kemudian, kita memanggil fungsi printPreorder untuk melakukan penelusuran preorder pada pohon dan mencetak hasilnya.</p>
<p>Dengan menggunakan pohon contoh ini, output dari program tersebut akan menjadi:</p>
<pre><code class="language-c++">Preorder traversal of binary tree is
1 2 4 5 3
</code></pre>
<h3> In Order</h3>

<ul>
<li>Source Code</li>
</ul>
<pre><code class="language-c++">

// C++ program for different tree traversals
#include &lt;bits/stdc++.h&gt;
using namespace std;
 
// A binary tree node has data, pointer to left child
// and a pointer to right child
struct Node {
    int data;
    struct Node *left, *right;
};
 
// Utility function to create a new tree node
Node* newNode(int data)
{
    Node* temp = new Node;
    temp-&gt;data = data;
    temp-&gt;left = temp-&gt;right = NULL;
    return temp;
}
 
// Given a binary tree, print its nodes in inorder
void printInorder(struct Node* node)
{
    if (node == NULL)
        return;
 
    // First recur on left child
    printInorder(node-&gt;left);
 
    // Then print the data of node
    cout &lt;&lt; node-&gt;data &lt;&lt; &quot; &quot;;
 
    // Now recur on right child
    printInorder(node-&gt;right);
}
 
// Driver code
int main()
{
    struct Node* root = newNode(1);
    root-&gt;left = newNode(2);
    root-&gt;right = newNode(3);
    root-&gt;left-&gt;left = newNode(4);
    root-&gt;left-&gt;right = newNode(5);
 
    // Function call
    cout &lt;&lt; &quot;Inorder traversal of binary tree is \n&quot;;
    printInorder(root);
 
    return 0;
}
</code></pre>
<ul>
<li>Penjelasan</li>
</ul>
<pre><code class="language-c++">struct Node {
    int data;
    struct Node *left, *right;
};
</code></pre>
<p>Node adalah struktur yang merepresentasikan simpul atau node dalam pohon biner. Setiap simpul memiliki data (variabel data), serta pointer ke simpul anak kiri (left) dan anak kanan (right).</p>
<pre><code class="language-c++">Node* newNode(int data)
{
    Node* temp = new Node;
    temp-&gt;data = data;
    temp-&gt;left = temp-&gt;right = NULL;
    return temp;
}

</code></pre>
<p>Fungsi newNode digunakan untuk membuat simpul baru dengan data tertentu. Fungsi ini mengalokasikan memori untuk simpul baru, mengatur nilai data, serta menginisialisasi pointer anak kiri dan anak kanan menjadi NULL.</p>
<pre><code class="language-c++">void printInorder(struct Node* node)
{
    if (node == NULL)
        return;

    // First recur on left child
    printInorder(node-&gt;left);

    // Then print the data of node
    cout &lt;&lt; node-&gt;data &lt;&lt; &quot; &quot;;

    // Now recur on right child
    printInorder(node-&gt;right);
}

</code></pre>
<p>Fungsi printInorder adalah implementasi dari penelusuran pohon dengan metode inorder. Prosesnya adalah sebagai berikut:</p>
<ul>
<li>Rekursif panggil printInorder untuk anak kiri simpul saat ini.</li>
<li>Cetak data dari simpul saat ini.</li>
<li>Rekursif panggil printInorder untuk anak kanan simpul saat ini.</li>
</ul>
<pre><code class="language-c++">int main()
{
    struct Node* root = newNode(1);
    root-&gt;left = newNode(2);
    root-&gt;right = newNode(3);
    root-&gt;left-&gt;left = newNode(4);
    root-&gt;left-&gt;right = newNode(5);

    // Function call
    cout &lt;&lt; &quot;Inorder traversal of binary tree is \n&quot;;
    printInorder(root);

    return 0;
}

</code></pre>
<p>Di dalam fungsi main, kita membuat pohon biner dengan beberapa simpul dan menyimpan alamat akar pohon pada variabel root. Kemudian, kita memanggil fungsi printInorder untuk melakukan penelusuran inorder pada pohon dan mencetak hasilnya.</p>
<p>Dengan menggunakan pohon contoh ini, output dari program tersebut akan menjadi:</p>
<pre><code class="language-c++">Inorder traversal of binary tree is
4 2 5 1 3

</code></pre>
<h3> Post Order</h3>

<ul>
<li>Source Code</li>
</ul>
<pre><code class="language-c++">

// C++ program for different tree traversals
#include &lt;bits/stdc++.h&gt;
using namespace std;
 
// A binary tree node has data, pointer to left child
// and a pointer to right child
struct Node {
    int data;
    struct Node *left, *right;
};
 
// Utility function to create a new tree node
Node* newNode(int data)
{
    Node* temp = new Node;
    temp-&gt;data = data;
    temp-&gt;left = temp-&gt;right = NULL;
    return temp;
}
 
// Given a binary tree, print its nodes according to the
// &quot;bottom-up&quot; postorder traversal.
void printPostorder(struct Node* node)
{
    if (node == NULL)
        return;
 
    // First recur on left subtree
    printPostorder(node-&gt;left);
 
    // Then recur on right subtree
    printPostorder(node-&gt;right);
 
    // Now deal with the node
    cout &lt;&lt; node-&gt;data &lt;&lt; &quot; &quot;;
}
 
// Driver code
int main()
{
    struct Node* root = newNode(1);
    root-&gt;left = newNode(2);
    root-&gt;right = newNode(3);
    root-&gt;left-&gt;left = newNode(4);
    root-&gt;left-&gt;right = newNode(5);
 
    // Function call
    cout &lt;&lt; &quot;Postorder traversal of binary tree is \n&quot;;
    printPostorder(root);
 
    return 0;
}
</code></pre>
<ul>
<li>Penjelasan</li>
</ul>
<pre><code class="language-c++">struct Node {
    int data;
    struct Node *left, *right;
};

</code></pre>
<p>Node adalah struktur yang merepresentasikan simpul atau node dalam pohon biner. Setiap simpul memiliki data (variabel data), serta pointer ke simpul anak kiri (left) dan anak kanan (right).</p>
<pre><code class="language-c++">
Node* newNode(int data)
{
    Node* temp = new Node;
    temp-&gt;data = data;
    temp-&gt;left = temp-&gt;right = NULL;
    return temp;
}
</code></pre>
<p>Fungsi newNode digunakan untuk membuat simpul baru dengan data tertentu. Fungsi ini mengalokasikan memori untuk simpul baru, mengatur nilai data, serta menginisialisasi pointer anak kiri dan anak kanan menjadi NULL.</p>
<pre><code class="language-c++">void printPostorder(struct Node* node)
{
    if (node == NULL)
        return;

    // First recur on left subtree
    printPostorder(node-&gt;left);

    // Then recur on right subtree
    printPostorder(node-&gt;right);

    // Now deal with the node
    cout &lt;&lt; node-&gt;data &lt;&lt; &quot; &quot;;
}

</code></pre>
<p>ChatGPT
Proses penelusuran pohon dengan metode postorder pada kode di atas dapat dijelaskan sebagai berikut:</p>
<p>Struktur Node:</p>
<p>cpp
Copy code
struct Node {
    int data;
    struct Node *left, *right;
};
Seperti sebelumnya, Node adalah struktur yang merepresentasikan simpul atau node dalam pohon biner. Setiap simpul memiliki data (variabel data), serta pointer ke simpul anak kiri (left) dan anak kanan (right).</p>
<p>Fungsi pembuatan simpul baru:</p>
<p>cpp
Copy code
Node* newNode(int data)
{
    Node* temp = new Node;
    temp-&gt;data = data;
    temp-&gt;left = temp-&gt;right = NULL;
    return temp;
}
Fungsi newNode digunakan untuk membuat simpul baru dengan data tertentu. Fungsi ini mengalokasikan memori untuk simpul baru, mengatur nilai data, serta menginisialisasi pointer anak kiri dan anak kanan menjadi NULL.</p>
<p>Fungsi postorder traversal:</p>
<p>cpp
Copy code
void printPostorder(struct Node* node)
{
    if (node == NULL)
        return;</p>
<pre><code>// First recur on left subtree
printPostorder(node-&gt;left);

// Then recur on right subtree
printPostorder(node-&gt;right);

// Now deal with the node
cout &lt;&lt; node-&gt;data &lt;&lt; &quot; &quot;;
</code></pre>
<p>}
Fungsi printPostorder adalah implementasi dari penelusuran pohon dengan metode postorder. Prosesnya adalah sebagai berikut:</p>
<ul>
<li>Rekursif panggil printPostorder untuk anak kiri simpul saat ini.</li>
<li>Rekursif panggil printPostorder untuk anak kanan simpul saat ini.</li>
<li>Cetak data dari simpul saat ini.</li>
</ul>
<pre><code class="language-c++">int main()
{
    struct Node* root = newNode(1);
    root-&gt;left = newNode(2);
    root-&gt;right = newNode(3);
    root-&gt;left-&gt;left = newNode(4);
    root-&gt;left-&gt;right = newNode(5);

    // Function call
    cout &lt;&lt; &quot;Postorder traversal of binary tree is \n&quot;;
    printPostorder(root);

    return 0;
}

</code></pre>
<p>Di dalam fungsi main, kita membuat pohon biner dengan beberapa simpul dan menyimpan alamat akar pohon pada variabel root. Kemudian, kita memanggil fungsi printPostorder untuk melakukan penelusuran postorder pada pohon dan mencetak hasilnya.</p>
<p>Dengan menggunakan pohon contoh ini, output dari program tersebut akan menjadi:</p>
<pre><code class="language-c++">
Postorder traversal of binary tree is
4 5 2 3 1
</code></pre>
<h1 id="3-dfs-dan-bfs">3. DFS dan BFS</h1>
<ul>
<li>BFS   : <a href="https://www.geeksforgeeks.org/breadth-first-search-or-bfs-for-a-graph/">https://www.geeksforgeeks.org/breadth-first-search-or-bfs-for-a-graph/</a></li>
<li>DFS   : <a href="https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/">https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/</a></li>
</ul>
<h4>BFS</h4>

<ul>
<li>Source Code</li>
</ul>
<pre><code class="language-c++">// C++ code to print BFS traversal from a given
// source vertex

#include &lt;bits/stdc++.h&gt;
using namespace std;

// This class represents a directed graph using
// adjacency list representation
class Graph {

    // No. of vertices
    int V;

    // Pointer to an array containing adjacency lists
    vector&lt;list&lt;int&gt; &gt; adj;

public:
    // Constructor
    Graph(int V);

    // Function to add an edge to graph
    void addEdge(int v, int w);

    // Prints BFS traversal from a given source s
    void BFS(int s);
};

Graph::Graph(int V)
{
    this-&gt;V = V;
    adj.resize(V);
}

void Graph::addEdge(int v, int w)
{
    // Add w to v’s list.
    adj[v].push_back(w);
}

void Graph::BFS(int s)
{
    // Mark all the vertices as not visited
    vector&lt;bool&gt; visited;
    visited.resize(V, false);

    // Create a queue for BFS
    list&lt;int&gt; queue;

    // Mark the current node as visited and enqueue it
    visited[s] = true;
    queue.push_back(s);

    while (!queue.empty()) {

        // Dequeue a vertex from queue and print it
        s = queue.front();
        cout &lt;&lt; s &lt;&lt; &quot; &quot;;
        queue.pop_front();

        // Get all adjacent vertices of the dequeued
        // vertex s.
        // If an adjacent has not been visited,
        // then mark it visited and enqueue it
        for (auto adjacent : adj[s]) {
            if (!visited[adjacent]) {
                visited[adjacent] = true;
                queue.push_back(adjacent);
            }
        }
    }
}

// Driver code
int main()
{
    // Create a graph given in the above diagram
    Graph g(4);
    g.addEdge(0, 1);
    g.addEdge(0, 2);
    g.addEdge(1, 2);
    g.addEdge(2, 0);
    g.addEdge(2, 3);
    g.addEdge(3, 3);

    cout &lt;&lt; &quot;Following is Breadth First Traversal &quot;
        &lt;&lt; &quot;(starting from vertex 2) \n&quot;;
    g.BFS(2);

    return 0;
}


</code></pre>
<ul>
<li>Penjelasan</li>
</ul>
<pre><code class="language-c++">class Graph {
   int V;
   vector&lt;list&lt;int&gt; &gt; adj;
public:
   Graph(int V);
   void addEdge(int v, int w);
   void BFS(int s);
};

</code></pre>
<p>Kelas Graph merepresentasikan graf menggunakan representasi daftar ketetanggaan (adjacency list). V adalah jumlah simpul, dan adj adalah vektor yang menyimpan daftar ketetanggaan setiap simpul.</p>
<pre><code class="language-c++">
Graph::Graph(int V) {
   this-&gt;V = V;
   adj.resize(V);
}
</code></pre>
<p>Fungsi konstruktor Graph digunakan untuk menginisialisasi jumlah simpul (V) dan mengalokasikan ruang untuk vektor adj.</p>
<pre><code class="language-c++">void Graph::addEdge(int v, int w) {
   adj[v].push_back(w);
}

</code></pre>
<p>Fungsi addEdge digunakan untuk menambahkan tepian (edge) ke graf. Ini menambahkan simpul w ke daftar ketetanggaan simpul v.</p>
<pre><code class="language-c++">void Graph::BFS(int s) {
   vector&lt;bool&gt; visited;
   visited.resize(V, false);
   list&lt;int&gt; queue;

   visited[s] = true;
   queue.push_back(s);

   while (!queue.empty()) {
      s = queue.front();
      cout &lt;&lt; s &lt;&lt; &quot; &quot;;
      queue.pop_front();

      for (auto adjacent : adj[s]) {
         if (!visited[adjacent]) {
            visited[adjacent] = true;
            queue.push_back(adjacent);
         }
      }
   }
}

</code></pre>
<p>Fungsi BFS adalah implementasi dari penelusuran dengan metode BFS. Prosesnya adalah sebagai berikut:</p>
<ul>
<li>Tandai simpul saat ini sebagai dikunjungi (visited[s] = true).</li>
<li>Masukkan simpul saat ini ke dalam antrian (queue.push_back(s)).</li>
<li>Selama antrian tidak kosong, lakukan langkah-langkah berikut:<ul>
<li>Ambil simpul dari depan antrian dan cetaknya (s = queue.front()).</li>
<li>Keluarkan simpul tersebut dari antrian (queue.pop_front()).</li>
<li>Untuk setiap simpul yang bertetangga dengan simpul saat ini dan belum dikunjungi, tandai sebagai dikunjungi dan masukkan ke dalam antrian.</li>
</ul>
</li>
</ul>
<pre><code class="language-c++">int main() {
   Graph g(4);
   g.addEdge(0, 1);
   g.addEdge(0, 2);
   g.addEdge(1, 2);
   g.addEdge(2, 0);
   g.addEdge(2, 3);
   g.addEdge(3, 3);

   cout &lt;&lt; &quot;Following is Breadth First Traversal &quot;
      &lt;&lt; &quot;(starting from vertex 2) \n&quot;;
   g.BFS(2);

   return 0;
}

</code></pre>
<p>Di dalam fungsi main, kita membuat graf dengan beberapa tepian menggunakan objek dari kelas Graph. Kemudian, kita memanggil fungsi BFS untuk memulai penelusuran dari simpul 2.</p>
<p>Dengan menggunakan graf contoh ini, output dari program tersebut akan menjadi</p>
<pre><code class="language-c++">
Following is Breadth First Traversal (starting from vertex 2) 
2 0 3 1
</code></pre>
<h4>DFS</h4>

<ul>
<li>Source Code</li>
</ul>
<pre><code class="language-c++">// C++ program to print DFS traversal from
// a given vertex in a  given graph
#include &lt;bits/stdc++.h&gt;
using namespace std;
 
// Graph class represents a directed graph
// using adjacency list representation
class Graph {
public:
    map&lt;int, bool&gt; visited;
    map&lt;int, list&lt;int&gt; &gt; adj;
 
    // Function to add an edge to graph
    void addEdge(int v, int w);
 
    // DFS traversal of the vertices
    // reachable from v
    void DFS(int v);
};
 
void Graph::addEdge(int v, int w)
{
    // Add w to v’s list.
    adj[v].push_back(w);
}
 
void Graph::DFS(int v)
{
    // Mark the current node as visited and
    // print it
    visited[v] = true;
    cout &lt;&lt; v &lt;&lt; &quot; &quot;;
 
    // Recur for all the vertices adjacent
    // to this vertex
    list&lt;int&gt;::iterator i;
    for (i = adj[v].begin(); i != adj[v].end(); ++i)
        if (!visited[*i])
            DFS(*i);
}
 
// Driver code
int main()
{
    // Create a graph given in the above diagram
    Graph g;
    g.addEdge(0, 1);
    g.addEdge(0, 2);
    g.addEdge(1, 2);
    g.addEdge(2, 0);
    g.addEdge(2, 3);
    g.addEdge(3, 3);
 
    cout &lt;&lt; &quot;Following is Depth First Traversal&quot;
            &quot; (starting from vertex 2) \n&quot;;
 
    // Function call
    g.DFS(2);
 
    return 0;
}
 
// improved by Vishnudev C
</code></pre>
<ul>
<li>Penjelasan</li>
</ul>
<pre><code class="language-c++">
class Graph {
public:
    map&lt;int, bool&gt; visited;
    map&lt;int, list&lt;int&gt; &gt; adj;

    void addEdge(int v, int w);
    void DFS(int v);
};
</code></pre>
<p>Kelas Graph merepresentasikan graf menggunakan representasi daftar ketetanggaan (adjacency list). visited adalah map yang digunakan untuk melacak simpul yang sudah dikunjungi. adj adalah map yang menyimpan daftar ketetanggaan setiap simpul.</p>
<pre><code class="language-c++">void Graph::addEdge(int v, int w)
{
    // Tambahkan w ke daftar ketetanggaan v.
    adj[v].push_back(w);
}

</code></pre>
<p>Fungsi addEdge digunakan untuk menambahkan tepian (edge) ke graf. Ini menambahkan simpul w ke daftar ketetanggaan simpul v.</p>
<pre><code class="language-c++">void Graph::DFS(int v)
{
    // Tandai simpul saat ini sebagai dikunjungi dan cetaknya.
    visited[v] = true;
    cout &lt;&lt; v &lt;&lt; &quot; &quot;;

    // Rekursif untuk semua simpul yang bertetangga
    // dengan simpul ini
    list&lt;int&gt;::iterator i;
    for (i = adj[v].begin(); i != adj[v].end(); ++i)
        if (!visited[*i])
            DFS(*i);
}

</code></pre>
<p>Fungsi DFS adalah implementasi penelusuran dengan metode DFS. Prosesnya adalah sebagai berikut:</p>
<ul>
<li>Tandai simpul saat ini sebagai dikunjungi (visited[v] = true).</li>
<li>Cetak simpul saat ini.</li>
<li>Lakukan Rekursif DFS untuk semua simpul yang bertetangga dengan simpul saat ini, asalkan simpul tersebut belum dikunjungi.</li>
</ul>
<pre><code class="language-c++">int main()
{
    // Buat graf sesuai dengan diagram yang diberikan
    Graph g;
    g.addEdge(0, 1);
    g.addEdge(0, 2);
    g.addEdge(1, 2);
    g.addEdge(2, 0);
    g.addEdge(2, 3);
    g.addEdge(3, 3);

    cout &lt;&lt; &quot;Following is Depth First Traversal&quot;
            &quot; (starting from vertex 2) \n&quot;;

    // Panggil fungsi DFS untuk memulai penelusuran dari simpul 2.
    g.DFS(2);

    return 0;
}

</code></pre>
<p>Di dalam fungsi main, kita membuat graf dengan beberapa tepian menggunakan objek dari kelas Graph. Kemudian, kita memanggil fungsi DFS untuk memulai penelusuran dari simpul 2.</p>
<p>Dengan menggunakan graf contoh ini, output dari program tersebut akan menjadi:</p>
<pre><code class="language-c++">
Following is Depth First Traversal (starting from vertex 2) 
2 0 1 3
</code></pre>
