# repositorio-introducao
#include <iostream>
#include <stdlib.h>
#include <time.h>
using namespace std;
int main() {
    srand(time(NULL));

  int opcao;

  do { // menu do jogo
    cout << "Selecione uma opcao:\n\
      1 - Jogar\n\
      2 - Sobre\n\
      3 - Sair\n";
    cin >> opcao; // by: Lucas

    switch (opcao) { // by: Natan
      case 1: // opcao jogar, inicia o jogo
        int a, b, c, d; // variaveis dos 4 digitos aleatorios
        int palpite;    // variavel do palpite

        do { // gera o 4 digitos aleatorios de 1 a 6 e diferentes
          a = rand() % 6 + 1;
          b = rand() % 6 + 1;
          c = rand() % 6 + 1;
          d = rand() % 6 + 1;
        } while (a == b || a == c || a == d || b == c || b == d || c == d); // by: Matheus R

        for (int t = 10; t > 0; t--) { // inicia o jogo
          cout << "\nDigite um numero de 4 digitos: "; // pede ao usuario um palpite, podendo escrever o valor sem o espaço entre os numeros
          cin >> palpite; // by: Matheus T

          int d1, d2, d3, d4; // cria 4 variaveis para separar a variavel "palpite" em milhar, centena, dezena e unidade
            d1 = (palpite / 1000);      // milhar
            d2 = (palpite / 100) % 10;  // centena
            d3 = (palpite / 10) % 10;   // dezena
            d4 = palpite % 10;          // unidade // by: Matheus T

          int posi_correta = 0; // cria a variavel para contabilizar os numeros que estao corretos e na posicao correta
            if (d1 == a) {
              posi_correta++; }
            if (d2 == b) {
              posi_correta++; }
            if (d3 == c) {
              posi_correta++; }
            if (d4 == d) {
              posi_correta++; } // by: Vitor

          int corretos_errados = 0; // cria a variavel para contabilizar os numeros que estao corretos porem na posicao errada
            if (d1 == b || d1 == c || d1 == d) {
              corretos_errados++; }
            if (d2 == a || d2 == c || d2 == d) {
              corretos_errados++; }
            if (d3 == a || d3 == b || d3 == d) {
              corretos_errados++; }
            if (d4 == a || d4 == b || d4 == c) {
              corretos_errados++; } // by: Natan

          if (posi_correta == 4) { // confere se a variavel "posi_correta" vale 4 mostrando que vc venceu se n ele passa e vai para as informacoes para o proximo round
            cout << "\nParabens voce venceu!\n\n";
            system("pause");
            system("cls");
            break; // by: Lucas
          }
