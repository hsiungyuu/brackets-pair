# brackets-pair
## 想法以及解法
------------
解題過程：<br>
>一開始會想左括號數應該要等於右括號數，但BUG出現了，你會發現 `))))((((` 也會成立，所以要換個想法。
<br>
<br>
首先你可以想成先找左括號，如果是「(」就push進去stack。
<br>
<br>
假如是「)」且stack的top等於「(」就進行pop，否則就把「)」push進stack
<br>
<br>
經過遍歷(就是從頭檢查一遍到尾巴)後如果stack是empty，答案就要輸出ture，反之輸出false。

------------

```cpp

#include<iostream>
#include<stack>
#include<string>

using namespace std;

int main(){
	ios::sync_with_stdio(0);cin.tie(0);
	string str; 
	cin >> str;
	stack<char> st;
	for(auto i:str){
		if(i == '(' ){
			st.push(i);
		}
		else{
			if(!st.empty() && st.top() == '(' )
				st.pop();
			else
				st.push(i);
		}
	}
	if(st.empty())
		cout<< "ture" << '\n';
	else 
		cout<< "false" << '\n';
	
	return 0;
}
```
