# WSQ-09_MultipartDataandFiles
This program reads the characters and lines that are inside a file .txt
#include<iostream>
#include<fstream>
#include<string>
using namespace std;

struct charlines {
  int characters, lines;
};
charlines countCharlines (charlines & num){
  string line;
  num.lines=0;
  num.characters=0;
  ifstream file("data.txt");
  if(file.is_open()) {
    while(getline(file, line)){
    num.lines ++;
    num.characters += line.size();
  }
  file.close();
}
return num;
}

int main () {
  charlines number;
  countCharlines(number);
  cout << "Total characters: " << number.characters << endl;
  cout << "Total lines: " << number.lines << endl;
  return 0;
}
