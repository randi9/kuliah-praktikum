
.cpp
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
