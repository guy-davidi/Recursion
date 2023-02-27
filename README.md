## Recursion
```
/*factorial - !*/
int fac(int n) {
	if (n == 0)
		return 1;
	else {
		return n*fac(n-1);	
	}

}
```
```
/* 1 1 2 3 5 8 13 21 ... */
/* fibonachi */
int fib(int n) {
	if (n == 1 || n==2)
		return n;
	return fib(n-1) + fib(n-2);
}
```
```
/* walking in tree */
void traverse(Node* node) {
    if (node == nullptr) {
        return;
    }
    // Process current node
    // Traverse left subtree
    traverse(node->left);
    // Traverse right subtree
    traverse(node->right);
}
```
```
/* merge sort */
void merge(int arr[], int l, int m, int r) {
    // Merge two subarrays
}

void mergeSort(int arr[], int l, int r) {
    if (l < r) {
        int m = l + (r - l) / 2;
        mergeSort(arr, l, m);
        mergeSort(arr, m + 1, r);
        merge(arr, l, m, r);
    }
}

int partition(int arr[], int low, int high) {
    // Partition array around pivot element
}

void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pivot = partition(arr, low, high);
        quickSort(arr, low, pivot - 1);
        quickSort(arr, pivot + 1, high);
    }
}
```
```
void moveDisk(int n, char fromRod, char toRod, char auxRod) {
    if (n == 1) {
        cout << "Move disk 1 from rod " << fromRod << " to rod " << toRod << endl;
        return;
    }
    moveDisk(n - 1, fromRod, auxRod, toRod);
    cout << "Move disk " << n << " from rod " << fromRod << " to rod " << toRod << endl;
    moveDisk(n - 1, auxRod, toRod, fromRod);
}
```
```
/* Generating all permutations of a set */
void permute(string str, int l, int r) {
    if (l == r) {
        cout << str << endl;
        return;
    }
    for (int i = l; i <= r; i++) {
        swap(str[l], str[i]);
        permute(str, l + 1, r);
        swap(str[l], str[i]);
    }
}
```
```
/*subset sum algo */
bool subsetSum(int set[], int n, int sum) {
    if (sum == 0) {
        return true;
    }
    if (n == 0 && sum != 0) {
        return false;
    }
    if (set[n - 1] > sum) {
        return subsetSum(set, n - 1, sum);
    }
    return subsetSum(set, n - 1, sum) || subsetSum(set, n - 1, sum - set[n - 1]);
}
```
```
/* Searching for an element in a binary search tree */
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node* left;
    struct node* right;
};

struct node* newNode(int data) {
    struct node* node = (struct node*) malloc(sizeof(struct node));
    node->data = data;
    node->left = NULL;
    node->right = NULL;

    return(node);
}

struct node* search(struct node* root, int key) {
    // Base Cases: root is null or key is present at root
    if (root == NULL || root->data == key)
       return root;

    // Key is greater than root's key
    if (root->data < key)
       return search(root->right, key);

    // Key is smaller than root's key
    return search(root->left, key);
}

int main() {
    struct node* root = newNode(4);
    root->left = newNode(2);
    root->right = newNode(5);
    root->left->left = newNode(1);
    root->left->right = newNode(3);

    int key = 5;
    struct node* result = search(root, key);
    if (result != NULL) {
        printf("%d found in the tree.\n", key);
    } else {
        printf("%d not found in the tree.\n", key);
    }

    return 0;
}
```
