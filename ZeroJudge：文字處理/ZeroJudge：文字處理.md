> 這邊會是我寫過，整理過的題目，那我答案都有附在上面。這邊的刷題進度會建議：
> - 平日2-3題
> - 假日3-5題

> 建議的寫題方式：
> - 依據題目，先到Zerojudge看題目
> - 先自己先試試看(或者是自己找找資料)花個5-10分鐘。
> -  沒轍的話就回來看解答。然後建議一邊看我解答，一邊自己寫一遍，跑一遍，在寫的時候盡量在旁邊撰寫自己的註釋，加油歐!!!!

## 1. a009. 解碼器

```python
char = list(input())

for i in range(len(char)):
     print(chr(ord(char[i])-7),end="")
```


## 2. a065. 提款卡密碼
```cpp
#include <iostream>
#include <cmath>    // for abs()
using namespace std;

int main() {
    string s;
    cin >> s;

    for (int i = 1; i < 7; i++) {
        int prev = s[i - 1] - 'A'; // 把字母轉成順序值
        int curr = s[i] - 'A';
        cout << abs(curr - prev);
    }
    cout << endl;
    return 0;
}
```
## 3. a149. 乘乘樂

```cpp
#include <iostream>
using namespace std;

int main() {
    int T;
    cin >> T;

    while (T--) {
        string num;
        cin >> num;

        int product = 1;
        for (char digit : num) {
            product *= (digit - '0');
        }

        cout << product << endl;
    }

    return 0;
}
```