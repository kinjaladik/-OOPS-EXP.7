# -OOPS-EXP.7
C++ program writing a generic stack using templates ,testing with int ,float and string

#include <iostream>
#include <string>
using namespace std;

template <class T>
class Stack {
private:
    static const int MAX = 5;
    T a[MAX];
    int top;

public:
    Stack() {
        top = -1;
    }
    void push(T x) {
        if (top == MAX - 1) {
            cout << "Stack Overflow\n";
        } else {
            a[++top] = x;
        }
    }
    void pop() {
        if (top == -1) {
            cout << "Stack Underflow\n";
        } else {
            cout << "Popped Element: " << a[top--] << "\n";
        }
    }
    void display() {
        if (top == -1) {
            cout << "Stack is Empty\n";
            return;
        }
        cout << "Stack Elements: ";
        for (int i = top; i >= 0; i--) {
            cout << a[i] << " ";
        }
        cout << "\n";
    }
};
int main() {
    Stack<int> s1;
    s1.push(10);
    s1.push(20);
    cout << "Integer Stack -> ";
    s1.display();
    s1.pop();
    s1.display();
    
    Stack<float> s2;
    s2.push(1.5f);
    s2.push(10.5f);
    cout << "Float Stack -> ";
    s2.display();
    s2.pop();
    s2.display();

    Stack<string> s3;
    s3.push("Hello");
    s3.push("World");
    cout << "String Stack -> ";
    s3.display();
    s3.pop();
    s3.display();

    return 0;
}
