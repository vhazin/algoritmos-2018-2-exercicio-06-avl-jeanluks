#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main(){
    int t,n,bst[200];
    scanf("%d", &t);
    while(t--) {
        scanf("%d", &n);
        for (int i = 0; i < n; ++i) {
            scanf("%d", &bst[i]);
        }
        int depth[250];
    memset(depth, 0, sizeof(depth));
    int x, i;
    for (int i = 0; i < n; ++i)
    {
        x = i;
        if(bst[x] != -1){
            while(1) {
                depth[x] = ((depth[2*x + 1] > depth[2*x + 2])? (depth[2*x + 1]) : (depth[2*x + 2])) + 1;
                if(x == 0)
                    break;
                x = (x - 1) / 2;
            }
        }
    }
    for (x = 0; x < n; ++x)
    {
        if(abs(depth[2*x + 1] - depth[2*x + 2]) > 1){
            printf("F\n");
        }

    }
    printf("T\n");

    }
    return 0;
}
