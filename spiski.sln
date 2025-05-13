#include <iostream> 
using namespace std; 
#include <string.h> 
 
struct Node { 
    int info; 
    Node* next; 
    Node(int info, Node* next) :info(info), next(next) {} 
    Node(int info) :info(info), next(nullptr) {} 
    Node() {} 
    friend ostream& operator<<(ostream& os, Node* head) { 
        for (Node* t = head; t != nullptr; t = t->next)os << t->info << " "; 
        return os; 
    } 
}; 
 
void add(Node*& head, int a) { // поставили &, чтобы можно было что-то присвоить и это появится в мэйне 
    Node* node = new Node(a, head); // создали новый узел 
    if (head == nullptr) { 
        head = node; 
        return; 
    } 
    node->next = head; 
    head = node; 
} 
 
void add1(Node*& head, int a) { 
    Node* node = new Node(a, head); // создали новый узел 
    head = node; 
} 
 
void addBegin(Node*& head, int a) { 
    Node* node = new Node(a, head); // создали новый узел 
    head = node; 
} 
 
void addEnd(Node*& head, int a) { 
    Node* node = new Node(a, head); // создали новый узел 
    if (head == nullptr) { 
        head = node; 
        return; 
    } 
    Node* t; 
    for (t = head; t->next != nullptr; t = t->next); 
    t->next = node; 
} 
 
void deleteList(Node*& head) { 
    if (head != nullptr) { 
        Node* t = head; 
        while (t) { 
            Node* g = t; 
            t = t->next; 
            //t = nullptr; 
            delete g; 
        } 
    } 
    head = nullptr; 
} 
 
// kopia spiska 
Node* listCopy(Node* head, Node*& tailCopy) { 
    Node* head1 = nullptr; 
    Node* prev = nullptr; 
    Node* tail = nullptr; 
    for (Node* h = head; h; h = h->next) { 
        tail = new Node(h->info); 
        if (!head1)prev = head1 = tail; 
        else prev->next = tail; 
        prev = tail; 
    } 
    tailCopy = tail; 
    return head1; 
} 
 
int insertList(Node* head, int x) { 
    Node* nodeX = nullptr; 
    Node* h; 
    for (h = head; h && h->info != x; h = h->next); 
    if (h) { 
        Node* tailCopy = nullptr; 
        Node* headCopy = listCopy(head, tailCopy); 
        tailCopy->next = h->next; 
        h->next = headCopy; 
        return 0; 
    } 
    else return -1; 
} 
 
bool digitInNode(Node* head, int x) { 
    Node* nodeX = nullptr; 
    Node* h; 
    for (h = head; h && h->info != x; h = h->next); 
    if (h) return true; 
    return false; 
} 
 
void delete_El(Node*& head) { 
    if (head == nullptr) { 
        return; 
    } 
    if ((head->info / 10) % 2 == 0) { 
        Node* help = head; 
        head = head->next; 
        delete help; 
    } 
    Node* head1 = head; 
    while (head1 != nullptr) { 
        if ((head1->next->info / 10) % 2 == 0) { 
            Node* help = head1->next; 
            head1->next = head1->next->next; 
            delete help; 
        } 
        head1 = head1->next; 
    } 
} 
 
void addEl(Node*& head, int x) { 
    Node* node = new Node(x); 
    if (head == nullptr) { 
        head = node; 
        return; 
    } 
    if (x < head->info) { 
        node->next = head; 
        head = node; 
        return; 
    } 
    /*if (head->next == nullptr) { 
        if (head->info > x) { 
            node->next = head; 
            head = node; 
            return; 
        } 
        else head->next = node; 
        return; 
    }*/ 
    Node* h = head; 
    for (; h->next != nullptr && h->next->info < x; h = h->next); 
    node->next = h->next; 
    h->next = node; 
} 
 
void delTwoEl(Node*& head) { 
    Node* h = head; 
    while (h->next) { 
        if (h->info == h->next->info) { 
            Node* next = h->next; 
            h->next = h->next->next; 
            delete next; 
        } 
        h = h->next; 
    } 
} 
 
int main() 
{    
    Node* head = nullptr; 
    //////////// add ///////////// 
    for (int i = 0; i < 10; i ++) { 
        addEl(head, i); 
    } 
    cout << head; 
    //addEl(head, 78); 
    //addEl(head, 27); 
    //addEl(head, -1); 
    addEl(head, 2); 
    //addEl(head, 2); 
    //addEl(head, 20); 
    //addEl(head, 95); 
    //cout << head; 
    delTwoEl(head); 
    cout <<"\n"<< head; 
    /*Node*tail; 
    Node* node = new Node(20, nullptr); 
    tail = new Node(30, nullptr); 
    node->next = tail; 
    tail->next = new Node(40); 
    tail->next->next = new Node(50); 
    tail->next->next->next = new Node(60); 
    cout << node;*/ 
     
    ////////////// delete ////////////// 
    /*delete_El(head); 
    cout << "\n"<< head;*/ 
 
         
    ////////////////// copy //////////////// 
    Node* tailCopy = nullptr; 
    Node* headCopy = listCopy(node, tailCopy); 
    cout << "\n copy " << headCopy << "\n tailCopy " << tailCopy; 
    /////////////// insertCopy /////////////// 
    if (insertList(head, 3)) cout << "\n after insert " << head; 
    ///////// x ////// 
    cout<< "\n is in list "<< digitInNode(node, 50); 
    //////////////// delete ////////////// 
    cout << "\n delete" << head; 
    delete_El(head);
    if (node == nullptr) cout <<"\n"<< "List is empty"; 
     
 
    //for (int i = 0; i < 10; i++) { 
    //    //add(head, i); 
    //    addEnd(head, i); 
    ////    tail = new Node(i, head);  // создали новый узел 
    ////    head = head; 
    //} 
    //cout << head; 
     
   /* Node* head1 = nullptr; 
    Node* prev = nullptr; 
    for (int i = 0; i < 10; i++) { 
        tail = new Node(i); 
        if (head1 == nullptr) prev = head1 = tail; 
        else prev->next = tail; 
        prev = tail; 
    } 
    cout << "\n tail is tail\n" << head1; 
 
    return 0;*/ 
}
