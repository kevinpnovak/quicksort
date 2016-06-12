# quicksort
quicksort C
int separa (int *v, int p, int r)
{
    int esq, dir, pivo, aux;
    esq = p;
    dir = r;
    pivo = v[p];
    while(esq<dir)
    {
        while(v[esq] <= pivo)
            esq++;
        while(v[dir] > pivo)
            dir--;
        if(esq < dir)
        {
            aux = v[esq];
            v[esq] = v[dir];
            v[dir] = aux;
        }
    }
    v[p] = v[dir];
    v[dir] = pivo;
    return dir;

}

void quicksort( int *v, int l, int r)
{
    int pivo;
    if(r<=l)return;
    pivo = separa(v, l, r);
    quicksort(v, l, pivo-1);
    quicksort(v, pivo+1, r);
}

