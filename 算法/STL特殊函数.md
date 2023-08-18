1.next_permutation(a,a+4) 数组前4个元素全排列。

```c++
int main(int argc, char** argv) {
	int a[4]={1,2,3,4};
	sort(a,a+4);
	do{
		//cout<<a[0]<<" "<<a[1]<<" "<<a[2]<<" "<<a[3]<<endl;
		for(int i=0;i<4;i++)
		    cout<<a[i]<<" ";
		cout<<endl;
	}while(next_permutation(a,a+4));
	return 0;
}
```



