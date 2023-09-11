#include<iostream>
#include<string>
#include<vector>
using namespace std;


void test1()
{
	//string的存取
	string str = "hello,world";
	for (int i = 0; i < str.size(); ++i)
	{
		cout << str[i] << endl;

	}
	cout << endl;
	for (int i = 0; i < str.size(); ++i)
	{
		cout << str.at(i) << " ";
	
	}
	cout << endl;
	str.at(1) = '1';
	str[0] = '22';
	for (int i = 0; i < str.size(); ++i)
	{
		cout << str[i] << endl;
	}
}
void test2()
{
	//string的插入和删除
	string str = "hello,world";
	str.insert(1, "111");
	cout << str << endl;
	str.erase(1, 3);//从第一个位置开始三个字符
	cout << str << endl;
}
void test3()
{
	//子串获取
	string str = "hello,world";
	string Substr = str.substr(1,3);
	//后面参数表示的是count，而非截至位置
	cout << Substr << endl;
	string email = "zhangsan@qq.com";
	int pos = email.find('@');
	string name = email.substr(0, pos);
	cout << name << endl;
}
void printvector(vector<int> v)
{
	for (vector<int>::iterator it = v.begin(); it != v.end(); ++it)
	{
		cout << *it;
	}
	cout << endl;
}
void test4()
{
	//默认构造 无参构造
	vector<int>v1;
	for (int i = 0; i < 10; ++i)
	{
		v1.push_back(i);
	}
	printvector(v1);
	//区间方式构造
	vector<int>v2(v1.begin(), v1.end());
	printvector(v2);
	//n个elem方式构造
	vector<int>v3(10, 100);//十个一百
	printvector(v3);
	//拷贝构造
	vector<int>v4(v3);
	printvector(v4);
	
}
void test5()
{
	vector<int>v1;
	for (int i = 0; i < 10; ++i)
	{
		v1.push_back(i);
	}
	printvector(v1);
	vector<int>v2 = v1;
	printvector(v2);
	vector<int>v3;
	v3.assign(v1.begin(), v1.end());
	printvector(v3);
}
void test6()
{
	vector<int>v1;
	for (int i = 0; i < 10; ++i)
	{
		v1.push_back(i);
	}
	if (v1.empty())
	{
		cout << "empty" << endl;
	}
	else {
		cout << "v1的容量" << v1.capacity() << endl;
		cout << "v1的大小" << v1.size() << endl;

	}
	//重新指定大小
	v1.resize(15, 100);//填充100
	printvector(v1);
}
void test7()
{
	vector<int>v1;
	v1.push_back(10);
	v1.push_back(20);
	v1.push_back(30);
	v1.push_back(40);
	v1.pop_back();
	printvector(v1);
	v1.insert(v1.begin(), 100);
	printvector(v1);
	v1.insert(v1.begin(), 2,1000);
	printvector(v1);
	v1.erase(v1.begin());
	printvector(v1);
	v1.clear();
	printvector(v1);
	
}
void test8()
{

	vector<int>v1;
	for (int i = 0; i < 10; ++i)
	{
		v1.push_back(i);
	}
	for (int i = 0; i < v1.size(); ++i)
	{
		cout<<v1[i]<<" ";
	}
	cout << endl;
	for (int i = 0; i < 10; ++i)
	{
		cout << v1.at(i) << " ";
	}
	cout << endl;
	cout <<v1.front()<< endl;
	cout <<v1.back()<< endl;
}
void test9()
{
	vector<int>v1;
	for (int i = 0; i < 10; ++i)
	{
		v1.push_back(i);
	}
	printvector(v1);
	vector<int>v2;
	for (int i = 10; i > 0; --i)
	{
		v2.push_back(i);
	}
	v1.swap(v2);
	printvector(v1);

}
void test10()
{
	vector<int>v1;
	v1.reserve(100000);//预留空间
	for (int i = 0; i < 100000; ++i)
	{
		v1.push_back(i);
	}
	int* p = NULL;
	int num = 0;
	if (p != &v1[0])
	{
		p = &v1[0];
		num++;
	}
	cout << num << endl;//开辟内存的次数

}
int main()
{
	//test1();//string的存取
	//test2();//string的插入和删除
	//test3();//子串获取
	//test4();//vector构造函数
	//test5();//赋值操作
	//test6();//vector容量和大小
	//test7();//插入和删除
	//test8();//数据存取
	//test9();//vector容器互换
	test10();//vector预留空间
	system("pause");
	return 0;
}