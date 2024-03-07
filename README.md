# Equipo1
#include <iostream>
using namespace std;

struct Calculadora{

    Calculadora (){

    }
    void pedir_num (float sec_num[], int lim){
        int x;
        for (x=0 ; x < lim ; x++){
            cin >> sec_num[x];
        }
    }
    float suma (float sec_num[], int lim) {
        float sum = 0.0;
        int x;
        for (x=0 ; x < lim ; x++){
            sum += sec_num[x];
        }
        return sum;
    }
    float resta (float sec_num[], int lim) {
        float res = sec_num[0];
        int x;
        for (x=1 ; x < lim ; x++){
            res -= sec_num[x];
        }
        return res;
    }
    float multiplicacion (float sec_num[], int lim){
        float multi = 1.0;
        int x;
        for (x=0 ; x < lim ; x++){
            multi *= sec_num[x];
        }
        return multi;
    }
    float division (float sec_num[]){
        float divi;
        divi = sec_num[0] / sec_num[1];
        return divi;
    }
};

int main (){
    struct Calculadora calculadora1;
    float sec_num [100];
    int lim,op;

    do{
        cout << "---> Menu <---" << endl;
        cout << "1.Sumar" << endl;
        cout << "2.Restar" << endl;
        cout << "3.Multiplicacion" << endl;
        cout << "4.Division" << endl;
        cout << "5.Salir" << endl;
        cin >> op;

        switch (op) {
            case 1:
                cout << "Ingresa cantidad de numeros a sumar" << endl;
                cin >> lim;
                cout << "Ingrese los numeros: " << endl;
                calculadora1.pedir_num(sec_num , lim);
                cout << "La suma es: " << calculadora1.suma (sec_num , lim) << endl;
            break;
            case 2:
                cout << "Ingressa la cantidad de numeros a restar" << endl;
                cin >> lim;
                cout << "Ingrese los numeros: " << endl;
                calculadora1.pedir_num(sec_num , lim);
                cout << "La resta es: " << calculadora1.resta(sec_num , lim) << endl;
            break;
            case 3:
                cout << "Ingressa la cantidad de numeros a mulyiplicar" << endl;
                cin >> lim;
                cout << "Ingrese los numeros: " << endl;
                calculadora1.pedir_num(sec_num , lim);
                cout << "La multiplicacion es: " << calculadora1.multiplicacion(sec_num , lim) << endl;
            break;
            case 4:
                cout << "Ingressa 2 numeros a dividir" << endl;
                calculadora1.pedir_num(sec_num , 2);
                cout << "La division es: " << calculadora1.division(sec_num) << endl;
            break;
            case 5:
                cout << "Bye" << endl;
            break;
            default: cout << "Opcion invalida";
        }
    }while (op != 5);
    return 0;
}
