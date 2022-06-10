# Praktikum

## Apel

```bash
#include<iostream>
using namespace std;

struct player_t {
    int id;
    string jenis;
    string warna;
    string rasa;
};

int main() {
    player_t player[] = {
    {
        1,
        "apel malang "
        "hijau "
        "manis "
    },
    {
        2,
        "äpel bandung "
        "merah "
        "manis "
    },
    {
        3,
        "apel sumedang "
        "putih "
        "manis "
    },
    {
        4,
        "apel subang "
        "hijau "
        "tawar "
    },
    {
        5,
        "apel jambi "
        "merah "
        "asam"
    }
};

int idApelTermanis = 4;

player[1].jenis = "Apel malang";

for (int i = 0; i < 5; i++) {
    
    if (player[i].id == idApelTermanis) {
        cout << "apel kurang manis nih " << player[i].jenis << "buang apelnya tidak enak \n";
        
        break;
        
    }
    
    cout << "apel termanis " << player[i].jenis << "enak dimakan" << player[i].rasa << "\n";
    }
}
```
                                                                                       
                                                                                       
## game pokemon
```bash
#include <iostream>
using namespace std;

#define TOMBOL_ATAS 72
#define TOMBOL_BAWAH 80
#define TOMBOL_KIRI 75
#define TOMBOL_KANAN 77

int main() {
    // Game pokemon
    
    int panjangPeta = 20; // x
    int lebarPeta = 25; // y
    
    int posisiKarakterY = 15;
    int posisiKarakterX = 4;
    
    cout << "Karakter ada di y:" << posisiKarakterY << ", x:" << posisiKarakterX << "\n";
    
    int peta[lebarPeta][panjangPeta] = {
        {8,8,8,8,8,8,1,1,1,1,1,1,1,1,1,1,1,1,1,1},
        {8,8,8,8,8,8,1,1,1,1,1,1,1,5,5,1,1,1,1,1},
        {8,8,8,1,1,1,1,1,1,1,1,1,1,5,5,1,1,1,1,1},
        {8,8,8,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1},
        {1,8,8,8,8,8,8,1,1,1,1,1,1,1,1,1,1,1,1,1},
        {1,1,8,8,8,8,8,1,1,1,1,1,1,4,4,4,4,1,1,1},
        {1,1,1,1,1,1,1,1,1,1,1,1,1,4,4,4,4,1,1,1},
        {1,1,1,5,5,1,1,1,1,1,4,4,4,4,4,4,4,1,1,1},
        {1,1,1,5,5,1,1,1,4,4,4,4,4,4,4,4,6,6,6,6},
        {1,1,5,5,1,1,1,1,4,4,4,4,4,4,4,4,4,1,1,1},
        {1,1,5,5,1,1,1,1,4,4,4,1,1,4,4,1,1,1,1,1},
        {1,1,1,1,1,1,1,1,4,4,4,1,1,1,1,1,1,1,1,1},
        {1,1,1,1,1,1,1,1,4,4,4,1,1,1,1,1,1,1,1,1},
        {1,1,1,1,1,1,1,1,1,1,6,1,1,1,1,1,1,1,1,1},
        {1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1},
        {1,1,1,1,1,1,1,1,1,1,6,1,1,1,1,1,1,1,1,1},
        {8,8,8,8,6,6,6,1,1,1,1,4,4,4,4,4,1,1,1,1},
        {8,8,8,8,6,6,6,6,1,1,8,8,8,8,8,1,1,1,1,1},
        {1,1,1,1,8,8,8,1,1,1,1,4,4,4,4,4,1,1,1,1},
        {1,1,1,1,8,4,4,4,1,1,1,1,1,6,6,6,1,1,1,4},
    };
    
    
    int arrowKey = 0;
    
   
    
    while(1) {
        // Input Keyboard
        cout << "Masukan arrow key ";
        cin >> arrowKey;
        cout << "Arrow key yang dimasukan " << arrowKey << "\n";
        
        // Aturan menggerakkan karakter ke atas
        if(arrowKey == 72 && (peta[posisiKarakterY-1][posisiKarakterX] == 1 || peta[posisiKarakterY-1][posisiKarakterX] == 4) && posisiKarakterY >= 0) {
            // Gerakkan karakter ke atas
            posisiKarakterY = posisiKarakterY-1;
        }
        
        // Aturan menggerakkan karakter ke bawah
        if(arrowKey == 80 && (peta[posisiKarakterY+1][posisiKarakterX] == 1 || peta[posisiKarakterY+1][posisiKarakterX] == 4) && posisiKarakterY < lebarPeta) {
            // Gerakkan karakter ke atas
            posisiKarakterY = posisiKarakterY+1;
        }
        
        // Aturan menggerakkan karakter ke kiri
        if(arrowKey == 75 && (peta[posisiKarakterY][posisiKarakterX-1] == 1 || peta[posisiKarakterY][posisiKarakterX-1] == 4) && posisiKarakterX >= 0) {
            // Gerakkan karakter ke atas
            posisiKarakterX = posisiKarakterX-1;
        }
        
        // Aturan menggerakkan karakter ke kanan
        if(arrowKey == 77 && (peta[posisiKarakterY][posisiKarakterX+1] == 1 || peta[posisiKarakterY][posisiKarakterX+1] == 4) && posisiKarakterX < panjangPeta) {
            // Gerakkan karakter ke atas
            posisiKarakterX = posisiKarakterX+1;
        }
        
        // Render grafik
        for(int y=0; y<lebarPeta; y++) {
            for(int x=0; x<panjangPeta; x++) {
                
                if(posisiKarakterX == x && posisiKarakterY == y) {
                    cout << 0 << " ";
                } else {
                    cout << peta[y][x] << " ";
                }
            }
            cout << "\n";
        }
    }
     
    
    return 0;
}
```

## hitung harga
``` bash
// Online C++ compiler to run C++ program online
#include <iostream>
using namespace std;

void hargaPembelian(int hargaSatuan, int jumlahBeli, int diskon) {
    int totalHarga = hargaSatuan * jumlahBeli;
    int totalDiskon = totalHarga * diskon / 100;
    int totalHargaDiDiskon = totalHarga - totalDiskon;
    
    cout << "total harga pembelian setelah di diskon: " << totalHargaDiDiskon;
}
int main() {
    hargaPembelian(8000, 6, 50);
    
    return 0;
}
```
