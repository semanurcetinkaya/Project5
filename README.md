# project5
#include<iostream>
#include<cstdlib>//rand.srand
#include<ctime>//time
using namespace std;
//rastgele sayı üretmek için bir fonksiyon
int randomNumberAccess() {
	srand(static_cast<unsigned int>(time(0)));//rastgele sayı için seed
	return rand() % 100 + 1;//1 ile 100 arasında bir sayı üretmek için
}
//oyun başlıyor
int main(){
	int randomNumber = randomNumberAccess();//rastgele sayı olustur
	int prediction;//kullanıcıdan alınan tahmin
	int tryingNumber = 0;//kaç tahmin yapıldugını tut
	cout << "I keep a number between (1-100).Try to predict!" << endl;
	while (true) {
		cout << "your prediction:";
		cin >> prediction;
		tryingNumber++;
		if (prediction < randomNumber) {
			cout << "please predict bigger number" << endl;
		}
		else if (prediction > randomNumber) {
			cout << "please predict lower number." << endl;
		}
		else {
			cout << "Congratulations!" << "Your prediction is correct in " << tryingNumber << "'th prediction"<<endl;
			break;//dogru tahmin edildi,döngüden çık
		}
	}

