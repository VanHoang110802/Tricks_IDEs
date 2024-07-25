```cpp
#include <bits/stdc++.h>
using namespace std;

using ULL = unsigned long long;
using LL = long long;
using LD = long double;
using DB = double;

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
#define to_upper(str) transform(all(str),str.begin(),::toupper)
#define to_lower(str) transform(all(str),str.begin(),::tolower)
// a=target variable, b=bit number to act upon 0-n
#define BIT_SET(a,b) ((a) |= (1ULL<<(b)))
#define BIT_CLEAR(a,b) ((a) &= ~(1ULL<<(b)))
#define BIT_FLIP(a,b) ((a) ^= (1ULL<<(b)))
// '!!' to make sure this returns 0 or 1
#define BIT_CHECK(a,b) (!!((a) & (1ULL<<(b))))
#define BITMASK_SET(x, mask) ((x) |= (mask))
#define BITMASK_CLEAR(x, mask) ((x) &= (~(mask)))
#define BITMASK_FLIP(x, mask) ((x) ^= (mask))
#define BITMASK_CHECK_ALL(x, mask) (!(~(x) & (mask)))
#define BITMASK_CHECK_ANY(x, mask) ((x) & (mask))

ULL random64()
{
    ULL n  = 0;
    int l = rand() % (RAND_MAX - 2) + 2;
    int r = rand() % (RAND_MAX) + rand() % 2;
    n = n | (ULL)r;
    n = n << 32;
    n = n | (ULL)l;
    return n;
}

template<typename T>
inline T gcd(T a, T b)
{
    T tmp;
    while(b)
    {
        tmp = a % b;
        a = b;
        b = tmp;
    }
    return a;
}

template<typename T>
inline T lcm(T a, T b)
{
    return a / gcd(a, b) * b;
}

template<typename T>
inline T Sqrt(T k)
{
    T r = sqrt(k) + 1;
    while(r * r > k)
    {
        --r;
    }
    return r;
}

template<typename T>
inline Cbrt(T k)
{
    T r = cbrt(k) + 1;
    while(r * r * r  > k)
    {
        --r;
    }
    return r;
}

template<typename T>
inline T Add_mod(T a, T b, T c = 1000000007) // a+b % M
{
    return ((a % c) + (b % c)) % c;
}

template<typename T>
inline T Sub_mod(T a, T b, T c = 1000000007) // a-b % M
{
    return ((a % c) - (b % c)) % c;
}

template<typename T>
inline T Mul_mod(T a, T b, T c = 1000000007) // a*b % M
{
    if (b == 0)
        return 0;

    T t = Mul_mod(a, b / 2, c) % c;

    if (b & 1)
        return ((t + t) % c + a % c) % c;
    else
        return (t + t) % c;
}

template<typename T>
inline T Pow_mod(T a, T b, T c = 1000000007) // // a^b % M
{
    if(b == 0)
        return 1LL;

    T half = Pow_mod(a, b / 2, c) % c;
    half = Mul_mod(half, half, c);

    if(b & 1) return Mul_mod(half, a, c);
    else return half;
}

template<typename T>
inline T Inverse_mod(T a, T c = 1000000007)
{
    return Pow_mod(a, c - 2, c);
}

template<typename T>
inline T Div_mod(T a, T b, T c = 1000000007)
{
    T inverse = InverseMod(b, c);
    return (a % c * inverse) % c;
}

template<typename T>
inline T Extended_euclid(T a, T b, T &x, T &y)
{
    T xx = 0, yy = 1;
    y = 0;
    x = 1;
    while(b)
    {
        T q = a / b, t = b;
        b = a % b;
        a = t;
        \
        t = xx;
        xx = x - q * xx;
        x = t;
        t = yy;
        yy = y - q * yy;
        y = t;
    }
    return a;
}

template<typename T>
inline T Point_distance_HorVer(T x1, T y1, T x2, T y2)
{
    return abs(x1 - x2) + abs(y1 - y2);
}

template<typename T>
inline T PointDistanceDiagonally(T x1, T y1, T x2, T y2)
{
    return sqrt((x2 - x1) * (x2 - x1) + (y2 - y1) * (y2 - y1));
}

template<typename T>
inline T PointDistanceMinimum(T x1, T y1, T x2, T y2)
{
    T tmp1 = abs(x1 - x2);
    T tmp2 = abs(y1 - y2);
    T tmp3 = abs(tmp1 - tmp2);
    T tmp4 = min(tmp1, tmp2);
    return tmp3 + tmp4;
}

template<typename T>
inline T PointDistance3D(T x1, T y1, T z1, T x2, T y2, T z2)
{
    return sqrt(square(x2 - x1) + square(y2 - y1) + square(z2 - z1));
}

template<typename T>
inline T Cube(T a)
{
    return a * a * a;
}

template<typename T>
inline T RectengularPrism(T a, T b, T c)
{
    return a * b * c;
}

template<typename T>
inline T Pyramid(T base, T height)
{
    return (1/3) * base * height;
}

template<typename T>
inline T Ellipsoid(T r1, T r2, T r3)
{
    return (4/3) * 3.14159265359 * r1 * r2 * r3;
}

template<typename T>
inline T IrregualarPrism(T base, T height)
{
    return base * height;
}

template<typename T>
inline T Sphere(T radius)
{
    return (4/3) * 3.14159265359 * radius * radius * radius;
}

template<typename T>
inline T CylinderB(T base, T height)
{
    return base * height;   // base and height
}

template<typename T>
inline T CylinderR(T radius, T height)
{
    return 3.14159265359 * radius * radius * height;   // radius and height
}

template<typename T>
inline T Cone(T radius,T base, T height)
{
    return (1/3) * 3.14159265359 * radius * radius * height;
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
