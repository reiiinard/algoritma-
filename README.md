#include <iostream>
#include <string>

using namespace std;
void tampilkanMenuSeminar() {
    cout << "Menu Seminar:" << endl;
    cout << "1. Seminar A (Rp 50.000)" << endl;
    cout << "2. Seminar B (Rp 75.000)" << endl;
    cout << "3. Seminar C (Rp 100.000)" << endl;
}
int hitungTotalBiaya(int hargaSeminar, int jumlahPeserta) {
    return hargaSeminar * jumlahPeserta;
}

int main() {
    const int hargaSeminarA = 50000;
    const int hargaSeminarB = 75000;
    const int hargaSeminarC = 100000;

    string namaPeserta;
    int pilihanSeminar;
    int jumlahPeserta;

    cout << "Masukkan nama peserta: ";
    getline(cin, namaPeserta);
    do {
        tampilkanMenuSeminar();
        cout << "Pilih seminar (1-3): ";
        cin >> pilihanSeminar;

        if (pilihanSeminar < 1 || pilihanSeminar > 3) {
            cout << "Pilihan tidak valid. Silakan pilih lagi." << endl;
        }

    } while (pilihanSeminar < 1 || pilihanSeminar > 3);

    cout << "Masukkan jumlah peserta: ";
    cin >> jumlahPeserta;

    int totalBiaya;
    switch (pilihanSeminar) {
        case 1:
            totalBiaya = hitungTotalBiaya(hargaSeminarA, jumlahPeserta);
            break;
        case 2:
            totalBiaya = hitungTotalBiaya(hargaSeminarB, jumlahPeserta);
            break;
        case 3:
            totalBiaya = hitungTotalBiaya(hargaSeminarC, jumlahPeserta);
            break;
        default:
            cout << "Pilihan tidak valid. Keluar dari program." << endl;
            return 1;
    }
    cout << "Terima kasih, " << namaPeserta << "!" << endl;
    cout << "Anda telah mendaftar seminar dengan total biaya Rp " << totalBiaya << endl;
    cout << "Silakan selesaikan pembayaran." << endl;

    return 0;
}
 
