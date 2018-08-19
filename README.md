lennonkc.github.io

#include<stdio.h>
#include<stdlib.h>
#include"Link.h"
#include<assert.h>
#include<iostream>
using namespace std;

Node* buyNode()
{
	Node* p = (Node*)malloc(sizeof(Node));
	assert(p != NULL);
	return p;
}
void initList(Node** well)
{
	*well = NULL;
}

bool isEmpty(Node* myList)
{
	if (myList == NULL)
		return true;
	else
		return false;
}
Status pushFront(Node** link, Data data)
{
	Node* p = buyNode();
	Node* q = *link;

	if (*link == NULL)
	{
		p->pre = NULL;
		p->data = data;
		p->next = *link;
		*link = p;
		return success;
	}
	if (*link != NULL)
	{
		p->pre = NULL;
		p->data = data;
		p->next = *link;
		p->next->pre = p;
		*link = p;
		return success;
	}
	return success;
}

Status pushBack(Node** link, Data data)
{
	if (NULL == link)
		return fail;
	Node *p = buyNode();
	Node *q;
	if (isEmpty(*link))
	{
		q = *link;
		*link = p;
		p->pre = NULL;
		p->data = data;
		p->next = q;
		return success;
	}
	else
	{
		q = *link;
		while ((q)->next)			//*link? (*link)->next?
		{
			q = (q)->next;
		}
		p->pre = q;
		q->next = p;
		p->data = data;
		p->next = NULL;
		return success;
	}
}
void printList(Node* myList)
{
	while (myList != NULL)
	{
		cout << myList->data << endl;
		myList = myList->next;
	}
}
void printList2(Node* myList)
{
	while (myList->next != NULL)
	{
		//	cout << myList->data << endl;
		myList = myList->next;
	}

	while (myList != NULL)
	{
		cout << myList->data << endl;
		myList = myList->pre;
	}

}
void cleanList(Node** link)
{
	while (NULL == link || NULL == *link)
		return;
	Node *p = buyNode();
	Node *q = buyNode();
	q = *link;
	while (q)
	{
		p = q;
		q = q->next;
		free(p);
	}
	return;
}
void cleanList2(Node** link)//清空单链表  递归从后往前删
{
	if (link == NULL || NULL == *link)
		return;
	if ((*link)->next)
	{
		cleanList2(&((*link)->next));
	}
	free(*link);
	*link = NULL;
}
Node* findNode(Node* myList, int i)//获取第i个结点的地址
{
	for (int k = 1; k < i; ++k)
	{
		myList = myList->next;
		if (myList->next == NULL)return myList;
	}
	return myList;
}
Status listInsert(Node** link, int i, Data data)//在位置i上插入数据
{
	if (NULL == link || NULL == *link || i < 0)
		return fail;
	Node* q = buyNode();
	Node* p = findNode(*link, i);
	if (i == 1)			//|| findNode(*link, i)->next == NULL
	{
		if (i == 1)
		{
			p->next = *link;
			if (*link != NULL)(*link)->next->pre = p;
			*link = p;
			p->pre = NULL;	//pushFront
		}
	}
	p->pre->next = q;
	q->pre = p->pre;
	q->data = data;
	q->next = p;
	p->pre = q;
	return success;
}

Status getElem(Node* myList, int i, Data *pData)//获取位置i上的元素
{
	if (NULL == myList || i < 0 || NULL == pData)
		return fail;
	*pData = findNode(myList, i)->data;
	return success;
}
Status listDelete(Node** link, int i, Data *pData)//删除第i个元素，并用pData返回其值
{
	if (NULL == link || i <= 0)
		return fail;
	if (1 == i || findNode(*link, i)->next == NULL)
	{
		Node *p = findNode(*link, i);
		*pData = p->data;
		if (1 == i) { p->next->pre = NULL; *link = p->next; }
		if (1 != i)p->pre->next = NULL;
		free(p);
		p = NULL;
	}
	Node* p = findNode(*link, i);
	*pData = p->data;
	p->pre->next = p->next;
	p->next->pre = p->pre;
	free(p);
	p = NULL;
	return success;
}

bool checkRound(Node* myList)//如果有环，返回true
{
	Node* p = myList, *q = myList;
	while (p || q)
	{
		p = p->next;
		q = q->next->next;
		if (p = q)return true;
	}return false;
}


/*
void cleanList2(Node** link);//清空单链表  递归从后往前删
Node* findNode(Node* myList, int i);//获取第i个结点的地址
Status listInsert(Node** link, int i, Data data);//在位置i上插入数据
Status getElem(Node* myList, int i, Data *pData);//获取位置i上的元素
Status listDelete(Node** link, int i, Data *pData);//删除第i个元素，并用pData返回其值
bool checkRound(Node* myList);//如果有环，返回true
*/



/*
if (isEmpty(*link))
{
q = *link;
*link = p;
p->pre = q;
p->data = data;
p->next = NULL;
return success;
}
if(!isEmpty(*link))
{
while((*link) != NULL)
{
*link = (*link)->next;
}
q = *link;
*link = p;
p->pre = q;
p->data = data;
p->next = NULL;
}return success;*/
/*
{
if (NULL == link)
return fail;
Node *p = buyNode();
p->data = data;
if (isEmpty(*link))
{
p->next = *link;
p->pre = NULL;
*link = p;
return success;
}
(*link)->pre = p;
p->next = *link;
p->pre = NULL;
*link = p;
return success;
}*/
/*p->pre = *link;
*link = p;
p->data = data;
p->next = q;*/

void circleLinkList(Node** head)//构建循环链表
{
	Node* p = *head;
	while (p->next != NULL)
	{
		p = p->next;
	}
	p->next = *head;
	(*head)->pre = p;
}

void BACKList(Node** head)
{

	if (head == NULL || (*head)->next == NULL)
		return;
	Node * p = (*head)->next, *q = *head, *init = *head;
	Node *last = NULL;
A:
	p = init->next; q = init;
	while (p->next != last)
	{
		p = p->next;
		q = q->next;
	}
	Node* num = p->next;
	p->next = q; 
	if (num == NULL)*head = p;
	last = q->next;
	if (last != init ->next)goto A;
	q->next = NULL;

}
v
