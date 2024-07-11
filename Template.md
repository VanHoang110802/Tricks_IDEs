```cpp
#pragma GCC optimize("O3,unroll-loops")
#pragma GCC target("avx2")
#include <bits/stdc++.h>
using namespace std;

typedef unsigned long long ull;
typedef long double ld;
typedef long long ll;
typedef double db;

#define FAST_IO ios_base::sync_with_stdio(0),cin.tie(0)
#define sz(a) ((int)(a).size())
#define present(t, x) (t.find(x)!=t.end())
#define all(a) (a).begin(),(a).end()
#define rall(a) (a).rbegin(),(a).rend()
#define uni(a) (a).erase(unique(all(a)),(a).end())
#define prec(n) fixed<<setprecision(n)
#define fi first
#define se second
#define pb push_back
#define pf push_front
#define eb emplace_back
#define mp make_pair
#define mt make_tuple
#define upper upper_bound
#define lower lower_bound
#define itr iterator
#define rtr reverse_iterator
#define mem(a,x) memset(a,x,sizeof(a))
#define memf(a) memset(a,0x3f,sizeof(a))
#define pq priority_queue
#define GetMask ((x >> i) & 1)
#define cntBit(n) __builtin_popcount(n)
#define to_upper(str) transform(all(str),str.begin(),::toupper)
#define to_lower(str) transform(all(str),str.begin(),::tolower)

const ll MOD = 1000000007;

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

template<class T>
inline T Sqrt(T k) // can bac hai su dung binary search
{
    T r = sqrt(k) + 1;
    while(r * r > k)
    {
        r--;
    }
    return r;
}

template<class T>
inline T Cbrt(T k) // can bac ba su dung binary search
{
    T r = cbrt(k) + 1;
    while(r * r * r > k)
    {
        r--;
    }
    return r;
}

template<class T>
inline T AddMod(T a, T b, T c = MOD)
{
    return ((a % c) + (b % c)) % c;
}

template<class T>
inline T SubMod(T a, T b, T c = MOD)
{
    return ((a % c) - (b % c)) % c;
}

template<class T>
inline T MultMod(T a, T b, T c = MOD)
{
    return ((a % c) * (b % c)) % c;
}

template<class T>
T multiply_modulo(T a, T b, T c = MOD) // a * b % M - co the doi dau + thanh -, *
{
    if (b == 0)
        return 0;

    T t = multiply_modulo(a, b / 2, c) % c;

    if (b & 1)
        return (AddMod(t, t, c) + a % c) % c;
    else
        return AddMod(t, t, c);
}

template<class T>
T pow_mod(T a, T b, T c = MOD) // a^b % M
{
    if (b == 0)
        return 1LL;

    T half = pow_mod(a, b / 2, c) % c;
    half = multiply_modulo(half, half, c);

    if (b & 1)
        return multiply_modulo(half, a, c);
    else
        return half;
}

template<class T>
T modulo_inverse(T a, T M = MOD) // nghich dao modulo
{
    return pow_mod(a, M - 2, M);
}

template<class T>
T DivMod(T a, T b, T c = MOD)
{
    T inverse = modulo_inverse(b, c);
    return (a % c * inverse) % c;
}

void XuLy()
{

}

int main()
{
#ifndef ONLINE_JUDGE
	freopen("input.txt", "r", stdin);
#endif

    FAST_IO;
    XuLy();
    return 0;
}

```
