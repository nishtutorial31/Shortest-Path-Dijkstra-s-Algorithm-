#include <stdio.h>
#define INF 999

int main() {
    int n = 4;
    int cost[4][4] = {
        {0,3,INF,7},
        {3,0,1,INF},
        {INF,1,0,2},
        {7,INF,2,0}
    };

    int dist[4] = {0, INF, INF, INF};

    for(int k=0;k<n-1;k++)
        for(int i=0;i<n;i++)
            for(int j=0;j<n;j++)
                if(dist[i] + cost[i][j] < dist[j])
                    dist[j] = dist[i] + cost[i][j];

    for(int i=0;i<n;i++)
        printf("%d ", dist[i]);

    return 0;
}
