# brackets-pair
## 想法以及解法
------------
## 解題過程:
一開始會想左括號數應該要等於右括號數，但BUG出現了，你會發現 `))))((((` 也會成立，所以要換個想法。
<br>
<br>
先檢查，如果是「(」就push進去stack。
<br>
<br>
否則，是「)」且stack的top等於「(」就進行pop，不是的話就直接輸出match fail
<br>
<br>
經過遍歷(就是從頭檢查一遍到尾巴)後如果stack是empty，答案就要輸出ture，反之輸出false。

------------
## 解法:
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
