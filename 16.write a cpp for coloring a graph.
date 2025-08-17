#include <iostream>
using namespace std;

const int MAX = 100;

int graph[MAX][MAX]; 
int degree[MAX];     
int result[MAX];     
bool available[MAX]; 

int main() {
    int V, E;
    cout << "Enter number of vertices: ";
    cin >> V;
    cout << "Enter number of edges: ";
    cin >> E;

    for (int i = 0; i < V; ++i)
        degree[i] = 0;

    cout << "Enter each edge (u v):\n";
    for (int i = 0; i < E; ++i) {
        int u, v;
        cin >> u >> v;
        graph[u][degree[u]++] = v;
        graph[v][degree[v]++] = u;
    }

    for (int i = 0; i < V; ++i)
        result[i] = -1;

    result[0] = 0;
    cout << "\nColoring process:\n";
    cout << "Vertex 0 ---> Color 0\n";

    for (int u = 1; u < V; ++u) {
        for (int i = 0; i < V; ++i)
            available[i] = false;

        for (int i = 0; i < degree[u]; ++i) {
            int neighbor = graph[u][i];
            if (result[neighbor] != -1)
                available[result[neighbor]] = true;
        }

        int cr;
        for (cr = 0; cr < V; ++cr)
            if (!available[cr])
                break;

        result[u] = cr;
        cout << "Vertex " << u << " ---> Color " << cr << endl;
    }

    return 0;
}
