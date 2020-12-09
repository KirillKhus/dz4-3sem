
## 22. Удалить заданное ребро и в модифицированном графе отсортировать вершины по возрастанию степени вершины.

## Алгоритм:

- проверка в глубину графа на связность

``` C
int is_con(int **v_arr, int *is_c_arr, int cur_v, int v_count){
    int ans = 0;
    for(int j = 0; j < v_count; ++j){
        if(v_arr[cur_v][j] && !is_c_arr[j]){
            is_c_arr[j] = 1;
            ans++;
            ans += is_con(v_arr, is_c_arr, j, v_count);
        }
    }
    return ans;
}

```

- Удаление ребра графа

``` C
 for(int i = 0; i < v_count; ++i){

        for(int j = i; j < v_count; ++j){

            int sup = v_arr[i][j];
            while(sup > 0){
                fprintf(file2, "%d -- %d;\n", i + 1, j + 1);
                sup--;
            }
        }
    }
```

## Структурная схема алгоритма

![Alt-текст](https://github.com/KirillKhus/dz4-3sem/blob/main/diagram_dz.jpg)

## Результат работы

![Alt-текст](https://github.com/KirillKhus/dz4-3sem/blob/main/consol.jpg)

## Исходный граф

![Alt-текст](https://github.com/KirillKhus/dz4-3sem/blob/main/graph1.png)

## Модифицированный граф

![Alt-текст](https://github.com/KirillKhus/dz4-3sem/blob/main/graph2.png)
