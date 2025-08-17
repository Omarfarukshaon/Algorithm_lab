#include <iostream>
#include <climits>
using namespace std;

const int MAX = 100;
int cost[MAX][MAX];
bool inMST[MAX];

int prims(int n) {
    int totalWeight = 0;
    int key[MAX], parent[MAX];
    for (int i = 0; i < n; i++) {
        key[i] = INT_MAX;
        inMST[i] = false;
    }

    key[0] = 0;
    parent[0] = -1;

    for (int count = 0; count < n; count++) {
        int u = -1;
        for (int i = 0; i < n; ++i)
            if (!inMST[i] && (u == -1 || key[i] < key[u]))
                u = i;

        inMST[u] = true;
        totalWeight += key[u];
        cout << "Add vertex " << u << " with edge weight " << key[u] << endl;

        for (int v = 0; v < n; v++) {
            if (cost[u][v] && !inMST[v] && cost[u][v] < key[v]) {
                key[v] = cost[u][v];
                parent[v] = u;
            }
        }
    }

    return totalWeight;
}

int main() {
    int n, e;
    cout << "Enter number of vertices: ";
    cin >> n;
    cout << "Enter number of edges: ";
    cin >> e;

    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            cost[i][j] = 0;

    cout << "Enter edges (format: u v weight):\n";
    for (int i = 0; i < e; i++) {
        int u, v, w;
        cin >> u >> v >> w;
        cost[u][v] = cost[v][u] = w;
    }

    int total = prims(n);
    cout << "Total weight of MST: " << total << endl;
    return 0;
}
