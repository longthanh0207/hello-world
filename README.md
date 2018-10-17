# hello-world
Kho lưu trữ đầu tiên
/* VCT lam cac viec
-nhap cac so n(nhieu) so nguyen
-xuat cac so nguyen
-chen them 1 so vao vi tri bat ky
-tim kiem 1 so trong ds cac so           => xong
-sua 1 so nguyen tai vi tri bat ky
-xoa 1 so nguyen trong day
-sap xep cac so nguyen tang dan
*/
#include<stdio.h>
// ham nay de nhap n so nguyen
void nhapMang(int a[],int n)
{
	for(int i=0;i<n;i++)
		scanf("%d",&a[i]);
}

// ham nay de xuat n so nguyen ra man hinh
void xuatMang(int a[],int n)
{
	for(int i=0;i<n;i++)
		printf("%4d",a[i]);
}

// ham nay de chen 1 so moi vao mang tai vi tri pos
void insert(int value, int pos, int a[],int n)
{
	//dich chuyen cac phan tu xuong 1 vi tri 
	for(int i=n-1;i>=pos;i--)
	{
		a[i+1]=a[i];
	}
	// chen value vao pos
	a[pos]=value;
}


// ham nay de tim 1 so trong array
// tra ve vitri tim thay dau tien
	findValue(int socantim,int a[],int n)
{
	for (int i=0;i<n; i++)
	{	
		if(a[i]==socantim)
			return i;
	}
	
	return -1;
}
// ham nay de tim nhi phan khi array co thu tu
// tra ve vitri tim thay
int search(int socantim,int a[],int n)
{
	int i=0;
	int j=n-1;
	do
	{
		int mid=(i+j)/2;
		if(socantim>a[mid])
			i=mid+1;
		else if(socantim<a[mid])
			j=mid-1;
		else
			return mid;
	}
	while(i<=j);
	
	
}



// ham nay de sua 1 so trong array tra ve 0 khi sua that bai


int update(int socansua, int sosausua, int a[],int n)
{
	int loc=findValue(socansua, a,n);
	if(loc==-1)
		return 0;
	else
	{
		a[loc] = sosausua;
		return 1;
	}
}


// ham nay de xoa 1 so tim thay dau tien khoi day
// x la so can xoa
DeleteValue(int x,int a[],int n)
{
	int pos=findValue(x,a,n);
	if(pos==-1)
		return n;// tra ve n la so phan tu nhu cu
		// dich chuyen cac phan tu
	for(int i=pos;i)
	
}
int main()
{
	// khai bao 1 array de chua 100 phan tu
	// cach 1
	int a[100];
	int n=5;
	// nhap n so nguyen
	nhapMang(a,n);
	xuatMang(a,n);
	// nhap value va pos de goi ham insert
	int pos,value;
	printf("\nnhap pos can chen");
	scanf("%d", &pos);
	printf("\nnhap value can chen");
	scanf("%d", &value);
	if(pos>=0 && pos<=n)
	{
		insert(value,pos,a,n);
		n=n+1; // n tang len 1 don vi da chen them 1 so moi
		xuatMang(a,n); // n+1 de xuat them 1 vitri so voi luc dau nhap
		
	}
	else
		printf("ko chen dc may oi, vi pos ky qua");
		
	
	int socantim;
	printf("\nnhap so can tim: ");
	scanf("%d", &socantim);
	
//	int location=findValue(socantim,a,n);
	int location=search(socantim,a,n);
	
	if (location==-1)
		printf("not found");
	else
		printf("\nthay no o vi tri %d", location);
		int socansua;
		printf("\nSo can sua: ");
		scanf("%d", &socansua );
		int sosausua;
		printf("\nSo sau sua: ");
		scanf("%d", &sosausua );
		int ketqua=update(socansua, sosausua,a,n);
		if(ketqua==0)
			printf("\nSua that bai ");
		else
		{
			printf("\nsua thanh cong");
			xuatMang(a,n);
		}
	
//	int *a=(int*)calloc(100,sizeof(int));
	return 1;
}
