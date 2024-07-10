```cpp
#pragma GCC optimize("O3,unroll-loops")
#pragma GCC target("avx2")
#include <bits/stdc++.h>
using namespace std;

typedef long long ll;
typedef long double lb;
typedef double db;

#define FAST_IO ios_base::sync_with_stdio(0),cin.tie(0)
#define sz(a) ((int)(a).size())
#define present(t, x) (t.find(x) != t.end)
#define all(a) (a).begin(),(a).end()
#define prec(n) fixed<<setprecision(n)
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
#define flo(a, b) (a/b)
#define cel(a, b) (a+b-1)

template<class T>
inline T AddMod(T a, T b, T c)
{
	return ((a % c) + (b % c)) % c;
}

template<class T>
inline T SubMod(T a, T b, T c)
{
	return ((a % c) - (b % c)) % c;
}

template<class T>
inline T MultMod(T a, T b, T c)
{
	return ((a % c) * (b % c)) % c;
}

ll pow_mod(ll a, ll b, ll M) // a^b
{
	ll res = 1LL;
	while(b)
	{
		if(b & 1LL)
		{
			res = MultMod(res, a, M);
		}
		a = MultMod(a, a, M);
		b /= 2LL;
	}
	return res;
}

template<class T>
inline T modulo_inverse(T a, T M) // nghich dao modulo
{
	return pow_mod(a, M - 2, M);
}

template<class T>
inline T DivMod(T a, T b, T c)
{
	T inverse = modulo_inverse(b, c);
	return (a % c * inverse) % c;
}

template<class T>
inline T gcd(T a, T b)
{
	while(b != 0)
	{
		swap(b, a %= b);
	}
	return a;
}

template<class T>
inline T lcm(T a, T b)
{
	return a / gcd(a, b) * b;
}

ll Sqrt(ll x) // sqrt use binary search
{
	ll ans = 0;
	for(ll k = 1LL << 30; k != 0; k /= 2)
	{
		if((ans + k) * (ans + k) <= x)
		{
			ans += k;
		}
	}
	return ans;
}

void XuLy()
{
	
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
