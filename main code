#include <iostream>
#include <fstream>
#include <ctime>
using namespace std;

bool estValideNomDeFichierTXT(std::string nomFichier) {
    std::string caracteresInterdits = "\\/:?\"<>|";
    for (char c : nomFichier) {
        if (caracteresInterdits.find(c) != string::npos) {
            return false;
        }
    }
    return true;
}


bool validerNombreDansIntervalle(long long nombre, long long debutIntervalle, long long finIntervalle) {
    return nombre >= debutIntervalle && nombre <= finIntervalle;
}

short lancer_De() {
    return rand() % 6 + 1;
}

int main() {
    string nomFichier;
    long long paramSrand, nombreDonnees;

    cout << "Entrez le nom d'un fichier sans extension: ";
    cin >> nomFichier;
    nomFichier += ".txt";

    if (!estValideNomDeFichierTXT(nomFichier)) {
        cout << "Nom de fichier invalide.";
        return 1;
    }

    cout << "Entrez un nombre entier pour srand: ";
    cin >> paramSrand;

    if (!validerNombreDansIntervalle(paramSrand, 0, 4294967295)) {
        cout << "Nombre invalide pour srand.";
        return 1;
    }

    cout << "Entrez un nombre entier pour le nombre de donnees: ";
    cin >> nombreDonnees;

    if (!validerNombreDansIntervalle(nombreDonnees, 21, 36000000)) {
        cout << "Nombre invalide pour le nombre de donnees.";
        return 1;
    }

    srand(time(NULL));
    //srand((unsigned int)paramSrand);
    ofstream fichierSortie(nomFichier);

    for (long long i = 0; i < nombreDonnees; ++i) {
        fichierSortie << lancer_De() << endl;
    }

    fichierSortie.close();
    cout << "Données générées avec succes.";

    return 0;
}
