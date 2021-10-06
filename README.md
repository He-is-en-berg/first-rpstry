# first-rpstry
#include<iostream>
using namespace std;

class Fraction {
    private:
        int n;
        int d;
    public:
        Fraction(int n, int d) { //constructor
            cout << "Obj created!" << endl;
            this -> n = n;
            this -> d = d;
        }
        void print() {
            cout << n << "/" << d << endl;
        }
        void simplify() {
            int i = min(n, d);
            for(; i>0; i--){
                if(n%i==0 && d%i==0) {
                    n = n/i;
                    d = d/i;
                    break;
                }
            }
        }
        void add(Fraction s2){ 
            n = s2.d*n + d*s2.n;
            d = d * s2.d;
            simplify();
        }
        ~Fraction() { //destructor
            cout << "as-tala-vista" << endl;
        }
};
