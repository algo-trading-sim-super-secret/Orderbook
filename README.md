This is a fork of the codebook by [Coding Jesus](https://github.com/Tzadiko/Orderbook/commit/dd136dd219ead95796f0e396e9e1395542bf673f) with changes for my use case.

# Running:
To run `main.cpp`
`g++-13 -g main.cpp Orderbook.cpp -o main --std=c++2b`

Changes:
```c++ 
void Orderbook::PruneGoodForDayOrders()
{
    ...
    /*localtime_s(&now_parts, &now_c);*/
    localtime_r(&now_c,&now_parts); // [][] Microsoft uses _s, linux uses _r
    ...
}
```
* Compatibility changes for using a different compiler version likely, like reinitalization of `_` in for loops


