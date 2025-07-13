#include <iostream>
#include <vector>
#include <queue>
#include <climits>
using namespace std;

vector<pair<int, int>> adjlist[6];
vector<int> dijk(int s, vector<pair<int, int>> adjlist[], int n) {
    vector<int> dist(n + 1, INT_MAX);
    dist[s] = 0;
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq; // Min-heap
    pq.push({0, s});

    while (!pq.empty()) {
        int distance = pq.top().first;
        int node = pq.top().second;
        pq.pop();

        for (auto edge : adjlist[node]) {
            int nextNode = edge.first;
            int weight = edge.second;

            if (dist[node] + weight < dist[nextNode]) {
                dist[nextNode] = dist[node] + weight;
                pq.push({dist[nextNode], nextNode});
            }
        }
    }
    return dist;
}

int main() {
    int V, E;
    cout << "Enter the number of vertices: ";
    cin >> V;
    cout << "Enter the number of edges: ";
    cin >> E;

    for (int i = 0; i < E; i++) {
        int v, w, weight;
        cout << "Enter edge (v w weight): ";
        cin >> v >> w >> weight;
        adjlist[v].push_back({w, weight});
        adjlist[w].push_back({v, weight}); // for undirected graphs
    }

    int start;
    cout << "Enter the starting vertex for Dijkstra's Algorithm: ";
    cin >> start;

    vector<int> result = dijk(start, adjlist, V);

    cout << "\nShortest distances from vertex " << start << ":" << endl;
    for (int i = 0; i < V; i++) {
        cout << "Vertex " << i << " -> Distance " << result[i] << endl;
    }
cout<<endl;
    return 0;
}
