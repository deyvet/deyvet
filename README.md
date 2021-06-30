#include <stdio.h>
#include <stdlib.h>
#include <math.h>
void somar(long long int N, long long int M, long long int *vetor){
    long long int i;
    long long int a, b, x;
    scanf("%lld %lld %lld", &a, &b, &x);

    if( (a < 1) || (b < 1) || (a > N) || (b > N) ){
        exit(1);
    }
    
    for(i = a - 1; i < b; i++){
        vetor[i]+=x;
    }
}

void subtrair(long long int N, long long int M, long long int *vetor){
    long long int i;
    long long int a, b, x;
    scanf("%lld %lld %lld", &a, &b, &x);

    if( (a < 1) || (b < 1) || (a > N) || (b > N) ){
        exit(1);
    }

    for(i = a - 1; i < b; i++){
        vetor[i]-=x;
    }
}

void imprimir(long long int N, long long int *vetor){
    long long int i;
    scanf("%lld", &i);
    if ( (i > pow(-10,18)) || (i > N) ){
        exit(1);
    }
    printf("%lld\n", vetor[i-1]);
}

int main(){
    long long int N, M;
    long long int *vetor;
    long long int i;
    int op;
    scanf("%lld %lld", &N, &M);
    if( (N < 1) || ( N > (pow (10, 7))) || (M < 1) || ( M > 1000) ){
        exit(1);
    }

    vetor = calloc(N, sizeof(long long int));

    for (i = 0; i < M; i++){
        scanf("%d", &op);
        switch (op){
        case 1:
            somar(N, M, vetor);
            break;
        case 2:
            subtrair(N, M, vetor);
            break;
        case 3:
            imprimir(N, vetor);
            break;
        default:
            break;
        }
    }
    
    free(vetor);
    return 0;
}
