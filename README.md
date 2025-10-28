#include <bits/stdc++.h>
using namespace std;
using ll = long long;

// --- マクロ ---
#define for(i,a,b) for(int i=(int)a; i<(int)b; i++)
#define FOR(i,a,b) for(int i=(int)a; i<=(int)b; i++)
#define all(v) (v).begin(), (v).end()
#define rall(v) (v).rbegin(), (v).rend()

// --- 汎用関数 ---
template<class T> bool chmin(T &a, const T &b){ if(a>b){ a=b; return true; } return false; }
template<class T> bool chmax(T &a, const T &b){ if(a<b){ a=b; return true; } return false; }

// --- 入出力省略用 read() ---
template<class... T>
void read(T&... args){ (cin >> ... >> args); }  // C++17 fold式で一気に読み取り

// --- 入出力省略 ---
#define in(...) int __VA_ARGS__; read(__VA_ARGS__)
#define inl(...) ll __VA_ARGS__; read(__VA_ARGS__)
#define out(x) cout << (x) << '\n'
#define out2(a,b) cout << (a) << " " << (b) << '\n'

// --- 定数 ---
const ll INF = 1LL << 60;
const int MOD = 1000000007;

// --- 重複削除（昇順）---
template <class T>
void uniq(vector<T> &v){
    sort(all(v));
    v.erase(unique(all(v)), v.end());
}

int main(){
    ios::sync_with_stdio(false);
    cin.tie(nullptr);
    in(D, N);  
    vector<int> S(D + 2, 0); 
    for(i, 0, N){
        in(L, R);     
        S[L] += 1;
        S[R + 1] -= 1;
    }
    for(i, 0, D){
        S[i + 1] += S[i];
    }
    for(i, 1, D + 1){
        out(S[i]);
    }
}
