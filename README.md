
***Creation of tree 
#include<stdio.h>
#include<stdlib.h>

struct node
{
    struct node*root;
    int data;

};

int main()
{
    struct node*root=0;
    root=make_node();
}
{
    struct node*left,*right,*nnode;
    nnode=(struct node*)malloc(sizeof(struct node));
    int ch;
    printf("enter the data and enter -1 to stop");
    scanf("%d",&ch);
    if(ch==-1)
    {
        return 0;
    }
    else
    {
        nnode->data=ch;
        printf("Enter the left child of %d";ch);
        nnode->left=make_node();
        printf("Enter the right child of %d";ch);
        nnode->right=make_node();
        return nnode;
    }
}


***To traverse pre , post , and inorder 
#include <stdio.h>
#include <stdlib.h>


struct Node {
    int data;
    struct Node* left;
    struct Node* right;
} Node;


 createNode(int data) { 
    struct node*nnode;
    nnode = (struct node*)malloc(sizeof(struct node));
    if (!newNode) {
        printf("Memory error\n");
        return NULL;
    }
    newNode->data = data;
    newNode->left = newNode->right = NULL;
    return newNode;
}


Node* insertNode(Node* root, int data) {
   
    if (root == NULL) {
        root = createNode(data);
        return root;
    }

    
    if (data < root->data) {
        root->left = insertNode(root->left, data);
    } else if (data > root->data) {
        root->right = insertNode(root->right, data);
    }

    return root;
}


void inorderTraversal(Node* root) {
    if (root != NULL) {
        inorderTraversal(root->left);
        printf("%d ", root->data);
        inorderTraversal(root->right);
    }
}


void preorderTraversal(Node* root) {
    if (root != NULL) {
        printf("%d ", root->data);
        preorderTraversal(root->left);
        preorderTraversal(root->right);
    }
}


void postorderTraversal(Node* root) {
    if (root != NULL) {
        postorderTraversal(root->left);
        postorderTraversal(root->right);
        printf("%d ", root->data);
    }
}

int main() {
    Node* root = NULL;

   
    root = insertNode(root, 8);
    root = insertNode(root, 3);
    root = insertNode(root, 10);
    root = insertNode(root, 1);
    root = insertNode(root, 6);
    root = insertNode(root, 14);
    root = insertNode(root, 4);
    root = insertNode(root, 7);
    root = insertNode(root, 13);

    
    printf("Inorder Traversal: ");
    inorderTraversal(root);
    printf("\n");

    printf("Preorder Traversal: ");
    preorderTraversal(root);
    printf("\n");

    printf("Postorder Traversal: ");
    postorderTraversal(root);
    printf("\n");

    return 0;
}

***To find height of binary tree
#include <stdio.h>
#include <stdlib.h>


struct Node {
    int data;
    struct Node* left;
    struct Node* right;
};


struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->left = NULL;
    newNode->right = NULL;
    return newNode;
}

int findHeight(struct Node* root) {
    if (root == NULL)
        return 0;
    else {
        int leftHeight = findHeight(root->left);
        int rightHeight = findHeight(root->right);
 return (leftHeight > rightHeight ? leftHeight : rightHeight) + 1;
    }
}

int main() {
    
    struct Node* root = createNode(1);
    root->left = createNode(2);
    root->right = createNode(3);
    root->left->left = createNode(4);
    root->left->right = createNode(5);

    
    printf("Height of the binary tree is: %d\n", findHeight(root));

    return 0;
}

***To find depth of binary tree
#include <stdio.h>
#include <stdlib.h>


struct Node {
    int data;
    struct Node* left;
    struct Node* right;
};


struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->left = NULL;
    newNode->right = NULL;
    return newNode;
}


int findDepth(struct Node* root) {
    if (root == NULL)
        return 0;

    int leftDepth = findDepth(root->left);
    int rightDepth = findDepth(root->right);

    return (leftDepth > rightDepth ? leftDepth : rightDepth) + 1;
}

int main() {
   
    struct Node* root = createNode(1);
    root->left = createNode(2);
    root->right = createNode(3);
    root->left->left = createNode(4);
    root->left->right = createNode(5);

    printf("Depth of the binary tree is: %d\n", findDepth(root));

    return 0;
}


      
