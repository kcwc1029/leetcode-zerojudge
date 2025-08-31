> 這邊會是我寫過，整理過的題目，那我答案都有附在上面。這邊的刷題進度會建議：
> - 平日2-3題
> - 假日3-5題

> 建議的寫題方式：
> - 依據題目，先到Zerojudge看題目
> - 先自己先試試看(或者是自己找找資料)花個5-10分鐘。
> -  沒轍的話就回來看解答。然後建議一邊看我解答，一邊自己寫一遍，跑一遍，在寫的時候盡量在旁邊撰寫自己的註釋，加油歐!!!!


## 1. a015. 矩陣的翻轉

```cpp
#include<iostream>
#include<vector>
using namespace std;
int main(){
    int r,c;
    while(cin>>r>>c){
        vector<vector<int>>matrix(105,vector<int>(105));
        for(int i=0;i<r;i++){
            for(int j=0;j<c;j++){
                cin>>matrix[i][j];
            }
        }
        for(int i=0;i<c;i++){
            for(int j=0;j<r;j++){
                cout<<matrix[j][i]<<" ";  //注意是 [j][i] 不是 [i][j] !
            }
            cout<<"\n";
        }
    }
    return 0;
}
```
## 2. a417. 螺旋矩陣

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

const int MAXN = 100;
int matrix[MAXN][MAXN];
int dx1[4] = {0, 1, 0, -1}; // 順時針方向（右、下、左、上）
int dy1[4] = {1, 0, -1, 0};

int dx2[4] = {1, 0, -1, 0}; // 逆時針方向（下、右、上、左）
int dy2[4] = {0, 1, 0, -1};

int main() {
    int T;
    cin >> T;
    while (T--) {
        int N, M;
        cin >> N >> M;

        // 初始化矩陣
        for (int i = 0; i < N; ++i)
            for (int j = 0; j < N; ++j)
                matrix[i][j] = 0;

        int x = 0, y = 0, dir = 0;
        for (int num = 1; num <= N * N; ++num) {
            matrix[x][y] = num;

            // 預測下一格位置
            int nx = x + (M == 1 ? dx1[dir] : dx2[dir]);
            int ny = y + (M == 1 ? dy1[dir] : dy2[dir]);

            // 若超出邊界或已填過，就轉向
            if (nx < 0 || ny < 0 || nx >= N || ny >= N || matrix[nx][ny] != 0) {
                dir = (dir + 1) % 4;
                nx = x + (M == 1 ? dx1[dir] : dx2[dir]);
                ny = y + (M == 1 ? dy1[dir] : dy2[dir]);
            }

            x = nx;
            y = ny;
        }

        // 輸出矩陣（寬度 5）
        for (int i = 0; i < N; ++i) {
            for (int j = 0; j < N; ++j) {
                cout << setw(5) << matrix[i][j];
            }
            cout << "\n";
        }
    }

    return 0;
}
```
## 3. b367. 翻轉世界

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    int t;
    cin >> t;

    while (t--) {
        int n, m;
        cin >> n >> m;

        vector<vector<int>> a; // 原始矩陣
        vector<vector<int>> b; // 180 度翻轉後的矩陣

        for (int i = 0; i < n; ++i) {
            vector<int> row(m);
            for (int j = 0; j < m; ++j) {
                cin >> row[j];
            }
            a.push_back(row);

            // 反轉每列後插入到 b 的開頭 → 等同於 Python 的 insert(0, arr[::-1])
            reverse(row.begin(), row.end());
            b.insert(b.begin(), row);
        }

        if (a == b)
            cout << "go forward" << endl;
        else
            cout << "keep defending" << endl;
    }

    return 0;
}
```


















