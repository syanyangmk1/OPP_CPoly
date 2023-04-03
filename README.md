# OPP_CPoly

#include <iostream>
using namespace std;

class CPoly{
protected:
int w, h;
public:
virtual int Area() = 0;
};

class CRect: public CPoly{
public:
CRect(int a, int b){w = a; h = b;}
int Area() override {return w * h;}

friend ostream& operator <<(ostream &os, CRect &r){
os << r.w << " " << r.h;
return os;
}
};

class CTri: public CPoly{
public:
CTri(int a, int b){w = a; h = b;}
int Area() override {return w * h / 2;}
};

int main(){
CRect r(4, 3);
CTri t(4, 3);
CPoly* p = nullptr;
p = &r;
cout << p->Area() << endl;
p = &t;
cout << p->Area() << endl;

CRect r2(2, 3);
cout << r2 << endl;
}




// 설명
위 코드는 CRect와 CTri 클래스에서 상속과 가상 함수, << 연산자의 오버로딩을 사용해서 면적을 계산하고 CRect 객체의 w와 h 값을 출력하는 코드입니다.

Cpoly의 멤버 변수 w와 h를 가지며 Area() 함수를 순수 가상 함수로 선언하고 해당 클래스의 변수를 CRect와 CTri가 상속을 받습니다.
main() 함수에서는 CRect와 CTri 클래스의 객체를 생성하고 CPoly 클래스 포인터 p를 선언하고 각각의 클래스에 저장한 이후 Area()함수를 호출합니다.
CRect 객체 r2를 생성하고 << 연산자를 이용하여 r2의 w와 h 값을 출력하게 합니다.
