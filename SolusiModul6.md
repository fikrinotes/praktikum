# Solusi Praktikum Algoritma dan Pemrograman Modul 6, 2023

### Solusi No. 1 dan No. 2
```cpp
#include <iostream>

using namespace std;

int main() {
	int n, m, u, v;

	cout << "input jumlah baris matriks pertama : ";
	cin >> n;
	cout << "input jumlah kolom matriks pertama : ";
	cin >> m;

	cout << "input jumlah baris matriks kedua : ";
	cin >> u;
	cout << "input jumlah kolom matriks kedua : ";
	cin >> v;

	int  m1[n][m];
	int m2[u][v];
	int hasil[n][m];
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
	for (int i = 0;i<n; i++ ) {
		for (int j = 0; j<m; j++) {
			cout<< "input elemen array :";
			cin >> m2[i][j];
		}
	}
	
	/*cetak matriks m2*/
	for (int i = 0;i<n; i++ ) {
		for (int j = 0; j<m; j++) {
			cout << m2[i][j] <<  " ";
		}
		cout << endl;
	}
	
	/*hitung penjumlahan matriks m1 + m2*/
	for (int i = 0;i<n; i++ ) {
		for (int j = 0; j<m; j++) {
			hasil[i][j] = m1[i][j] + m2[i][j];
		}
	}

	/*tampilkan hasil penjumlahan*/
	cout << "Hasil Penjumlahan : " << endl;
	for (int i = 0;i<n; i++ ) {
		for (int j = 0; j<m; j++) {
			cout << hasil[i][j] <<  " ";
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





### solusi No. 3

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
