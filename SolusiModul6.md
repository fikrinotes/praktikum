# Solusi Praktikum Algoritma dan Pemrograman Modul 6, 2023

berikut adalah solusi untuk modul 6 pada praktikum algoritma dan pemrograman departemen matematika dan sains data Universitas Andalas

### Solusi No. 1 dan No. 2

#### Bahasa Pemrograman : C++ 
##### Penjumlahan matriks (No. 1)
```cpp
#include <iostream>

using namespace std;

int main() {
	int n, m;

	cout << "input jumlah baris matriks : ";
	cin >> n;
	cout << "input jumlah kolom matriks : ";
	cin >> m;

	int A[n][m];
	int B[n][m];
	int hasil[n][m];
	int hasilkali[n][m];


	/*input elemen matriks A  */
	for (int i = 1;i<=n; i++ ) {
		for (int j = 1; j<=m; j++) {
			cout<< "A["<<i<<","<<j<<"] :";
			cin >> A[i][j];
		}
	}


	/*cetak matriks*/
	
	cout<< "~ Matriks A ~"<<endl;
	for (int i = 1;i<=n; i++ ) {
		for (int j = 1; j<=m; j++) {
			cout << A[i][j] <<  " ";
		}
		cout << endl;
	}


	/*input elemen matriks B  */
	for (int i = 1;i<=n; i++ ) {
		for (int j = 1; j<=m; j++) {
			cout<< "B["<<i<<","<<j<<"] :";
			cin >> B[i][j];
		}
	}


	/*cetak matriks*/
        cout << "~ Matriks B ~"<<endl;
	for (int i = 1;i<=n; i++ ) {
		for (int j = 1; j<=m; j++) {
			cout << B[i][j] <<  " ";
		}
		cout << endl;
	}

	/*hitung penjumlahan matriks A + B*/
	for (int i = 1;i<=n; i++ ) {
		for (int j = 1; j<=m; j++) {
			hasil[i][j] = A[i][j] + B[i][j];
		}
	}

	/*tampilkan hasil penjumlahan*/
	cout << "Hasil Penjumlahan : " << endl;
	for (int i = 1;i<=n; i++ ) {
		for (int j = 1; j<=m; j++) {
			cout << hasil[i][j] <<  " ";
		}
		cout << endl;
	}

}
```

##### Perkalian Matriks (No. 2)
```pascal
#include <iostream>

using namespace std;

int main() {
	int n, m, u, v;

	cout << "input jumlah baris matriks pertama : ";
	cin >> n;
	cout << "input jumlah kolom matriks pertama : ";
	cin >> m;

	
	do {
	cout << "input jumlah baris matriks kedua : ";
	cin >> u;
	} while (m != u);

	cout << "input jumlah kolom matriks kedua : ";
	cin >> v;


	int  m1[n][m];
	int m2[u][v];
	int hasilkali[n][m];
	

	/*input elemen matriks m1  */
	for (int i = 0;i<n; i++ ) {
		for (int j = 0; j<m; j++) {
			cout<< "input elemen array :";
			cin >> m1[i][j];
		}
	}


	/*cetak matriks*/
	for (int i = 0;i<n; i++ ) {
		for (int j = 0; j<m; j++) {
			cout << m1[i][j] <<  " ";
		}
		cout << endl;
	}
	

	/*input matriks m2  */
	for (int i = 0;i<u; i++ ) {
		for (int j = 0; j<v; j++) {
			cout<< "input elemen array :";
			cin >> m2[i][j];
		}
	}
	
	/*cetak matriks m2*/
	for (int i = 0;i<u; i++ ) {
		for (int j = 0; j<v; j++) {
			cout << m2[i][j] <<  " ";
		}
		cout << endl;
	}
	
	/* hitung hasil kali m1*m2 */
	cout << "Hasil Kali : "<<endl;
	for (int i = 0;i<n; i++ ) {
		for (int j = 0; j<m; j++) {
			hasilkali[i][j] = 0;
			for (int k = 0; k < m; k++) {
				hasilkali[i][j] += m1[i][k] *  m2[k][j];
			}
		}
	}

	/*tampilkan hasil perkalian matriks*/
	for (int i = 0;i<n; i++ ) {
		for (int j = 0; j<m; j++) {
			cout << hasilkali[i][j] <<  " ";
		}
		cout << endl;
	}

}
```

#### Bahasa Pemrograman : Pascal
##### Penjumlahan Matriks (No. 1)
```pascal
Program Penjumlahan_Matriks;
uses crt;
var a,b,c: array[1..10,1..10] of integer;
    pilihan,m,n,k,l: integer;
begin
   clrscr;
   write('Input jumlah baris matriks : ');
   Repeat
        gotoxy(32,1); clreol; readln(n);
   until  (n>0) ;
   write('Input jumlah kolom matriks : ');
   Repeat
        gotoxy(32,2); clreol; readln(m)
   until  (m>0) ;
   clrscr;
   gotoxy(7,1); writeln('========= Matrik A =========');
   for k:=1 to n do
     for l:=1 to m do
     begin
         gotoxy(8*l+3,k+2); write('A[',k,',',l,'] = '); readln(a[k,l]);
         gotoxy(8*l+3,k+2); clreol; write(a[k,l]);
     end;
   gotoxy(7,8); writeln('========= Matrik B =========');
   for k:=1 to n do
     for l:=1 to m do
     begin
         gotoxy(8*l+3,k+8); write('B[',k,',',l,'] = '); readln(b[k,l]);
         gotoxy(8*l+3,k+8); clreol; write(b[k,l]);
     end;
   writeln;
       gotoxy(7,17); writeln('========= Matrik C =========');
       for k:= 1 to n do
         for l:= 1 to m do
           begin
             c[k,l]:= a[k,l]+b[k,l];
             gotoxy(8*l+3,k+17); write(c[k,l]);
           end;
   readln;
end.
```

##### Perkalian Matriks (No. 2)
```pascal
Program Perkalian_Matriks;
uses crt;
var a,b,c: array[1..10,1..10] of integer;
    pilihan,m,n,p,q,k,l,x: integer;
begin
   clrscr;
   write('Input jumlah baris matriks A : ');
   Repeat
        gotoxy(34,1); clreol; readln(n);
   until  (n>0) ;
   write('Input jumlah kolom matriks A : ');
   Repeat
        gotoxy(34,2); clreol; readln(m)
   until  (m>0) ;
   write('Input jumlah baris matriks B : ');
   Repeat
        gotoxy(34,3); clreol; readln(p);
   until  (n>0) and(p=m) ;
   write('Input jumlah kolom matriks B : ');
   Repeat
        gotoxy(34,4); clreol; readln(q)
   until  (m>0);

   clrscr;
   gotoxy(7,1); writeln('========= Matrik A =========');
   for k:=1 to n do
     for l:=1 to m do
     begin
         gotoxy(8*l+3,k+2); write('A[',k,',',l,'] = '); readln(a[k,l]);
         gotoxy(8*l+3,k+2); clreol; write(a[k,l]);
     end;
   gotoxy(7,8); writeln('========= Matrik B =========');
   for k:=1 to p do
     for l:=1 to q do
     begin
         gotoxy(8*l+3,k+8); write('B[',k,',',l,'] = '); readln(b[k,l]);
         gotoxy(8*l+3,k+8); clreol; write(b[k,l]);
     end;
   writeln;
       gotoxy(7,17); writeln('========= Matrik C =========');
       for k:= 1 to n do
         for l:= 1 to q do
           begin
             c[k,l]:=0;
             for x:=1 to m do
               c[k,l]:=c[k,l]+(a[k,x]*b[x,l]);
               gotoxy(8*l+3,k+17); write(c[k,l]);
           end;
   readln;
end.
```




### solusi No. 3

#### Bahasa Pemrograman : C++
```cpp
#include <iostream>

using namespace std;

int main() {
	int x[5] = {1, 2, 3, 4, 5};
	int y[5] = {2, 4, 6, 8, 10};
	int n;
	int sx, sy, sxx, sxy;
	float a, b;

	n = sizeof(x);
	/*menghitung sigma x*/
	sx = 0;
	for (int i = 0; i<5; i++) {
		sx += x[i];
	}
	
	sy = 0;
	/*menghitung sigma y*/
	for (int i = 0; i<5; i++) {
		sy += y[i];
	}
	
	sxx = 0;
	/*menghitung sigma x^2*/
	for (int i = 0; i<5; i++) {
		sxx += x[i]*x[i];
	}

	sxy = 0;
	/*menghitung sigma xy*/
	for (int i = 0; i<5; i++) {
		sxy += x[i]*y[i];
	}

	a = (sy*sxx-sx*sxy) /(n*sxx-(sx*sx));
	b = (n*sxy-sx*sy)/(n*sxx-(sx*sx));
	
	cout << "nilai a = " << a << " dan nilai b = " << b;

}
```

#### Bahasa Pemrograman : Pascal

```pascal
uses crt;
var
DATA : array[1..2,1..10] of integer;
sigma : array[1..4] of integer;
n,m,i,j : integer;
a,b : real;
begin
clrscr;
Gotoxy(26,1); Writeln('INPUT ENTRI-ENTRI DATA');
Gotoxy(5,3);Write('Jumlah DATA <<Maks 10>>: ');
repeat gotoxy(40,3);clreol; readln(m);
until (m>0) and (m<=10);
writeln;
For i := 1 to 2 do
begin
Writeln('Input Data ', chr(87+i), ' : ');
For j := 1 to m do
Begin
write('data ', j,' : ');readln(data[i,j]);
end;
writeln;
end;
i := 1;
// sigma[1] = sigma(x), sigma[2] = sigma(y), sigma(3) = sigma(xy), sigma(4) = sigma(x^2)
while(i <=4) do
begin
if (i = 4) then
begin
for j := 1 to m do
begin
sigma[i] := sigma[i] + data[1,j] + data[2,j];
end;
end
else
begin
if(i=3) then
begin
sigma[i] := sigma[i] + sqr(data[1,j]);
end
else
begin
for j := 1 to m do
begin
sigma[i] := sigma[i] + data[i,j];
end;
end
end;
i := i + 1;
end;
a := ((sigma[2]*sigma[3])-(sigma[1]*sigma[4]))/((m*sigma[3]) - sqr(sigma[1]));
b := ((m*sigma[4])-(sigma[1]*sigma[2]))/((m*sigma[3]) - sqr(sigma[1]));
writeln;
writeln('Nilai dari a = ',a:10:2);
writeln('Nilai dari b = ',b:10:2);
readln;
end.
```
