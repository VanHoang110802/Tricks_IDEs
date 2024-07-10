```cpp
#pragma GCC optimize("O3,unroll-loops")
#pragma GCC target("avx2")
#include <bits/stdc++.h>
using namespace std;

typedef long long ll;
typedef long double lb;

#define FAST_IO ios_base::sync_with_stdio(0),cin.tie(0)
#define sz(a) ((int)(a).size())
#define present(t, x) (t.find(x) != t.end)
#define all(a) (a).begin(),(a).end()
#define prec(n) fixed<<setpecision(n)
#define fi first
#define se second
#define pb push_back
#define pf push_front
#define eb emplace_back
#define mp make_pair
#define upper upper_bound
#define lower lower_bound
#define itr iterator
#define mem(a,x) memset(a,x,sizeof(a))
#define memf(a) memset(a,0x3f,sizeof(a))
#define pq priority_queue
#define GetMask ((x>>i)&1)
#define cntBit(n) __builtin_popcount(n)
#define to_upper(str) transform(all(str),str.begin(),::toupper)
#define to_lower(str) transform(all(str),str.begin(),::tolower)

template<class T> inline T AddMod(T a, T b, T c)  { return ((a % c) + (b % c)) % c; }
template<class T> inline T SubMod(T a, T b, T c)  { return ((a % c) - (b % c)) % c; }
template<class T> inline T MultMod(T a, T b, T c) { return ((a % c) * (b % c)) % c; }

ll pow_mod(ll a, ll b, ll M)
{
    ll res = 1LL;
    while(b)
    {
        if(b & 1LL) { res = MultMod(res, a, M); }

        a = MultMod(a, a, M);
        b /= 2LL;
    }
    return res;
}

template<class T> inline T modulo_inverse(T a, T M) { return pow_mod(a, M - 2, M); } // nghich dao modulo
template<class T> inline T DivMod(T a, T b, T c) { T inverse = modulo_inverse(b, c); return (a % c * inverse) % c; }

void XuLy()
{
	ll a, b; cin >> a >> b;
	ll ans = pow_mod(a, b, 1000000007);
	cout << ans << '\n';
}

int main()
{
#ifndef Van_Hoang
	freopen("input.txt", "r", stdin);
#else
#endif

	FAST_IO;
	XuLy();
	return 0;
}
```
