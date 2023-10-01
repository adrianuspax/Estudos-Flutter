# Objetivo
Estudos e aprendizagem sobre o Flutter
# Dart
## Configurando o VSCode
**Passo 01:** Com o VSCode aberto, vamos configurar o Dart. Na aba lateral, clique no símbolo com quatro quadradinhos de “Extensões”.

![[a001-poa-006.png]]

**Passo 02:** Nesta sessão, você pode procurar por extensões e temas para personalizar seu VSCode. Vamos buscar por “Dart” no campo de busca. Estamos buscando uma extensão chamada “Dart”, desenvolvida por “Dart Code”, que possui um símbolo de certificação. Quando encontrá-la, clique em “Install”.
![[a001-poa-007.png]]

**Passo 03:** Com a extensão instalada, podemos criar um projeto Dart pressionando a tecla “F1” no teclado, e pesquisando por “Dart”, depois selecionamos a opção “Dart: New Project”. Depois, vamos selecionar o tipo de aplicação que vamos criar, podemos escolher a opção “Simple Console Application”. Por fim, selecionamos um diretório. Nosso projeto Dart será criado.

![[a001-poa-008.png]]

**Passo 04:** Para rodar nossa aplicação, podemos abrir um novo terminal, clicando em “Terminal” na Barra de Menus e nas opções que se abrem, clicamos em “New Terminal”. Com o terminal aberto abaixo, escrevemos “dart run” e damos um “Enter” no teclado.
![[Pasted image 20230930221709.png]]

## Variáveis
```dart
int value = 7;
int hex = 0x00001A; //Aceita hexadecimal
```

```dart
double value = 1.6;
double grand = 78e7; //motação decimal = 78000000.0
```

```dart
bool simple = true;
bool value = (grand == hex);
```

```dart
String value = 'somethig';
String value = "somethig"; // Funciona com aspas duplas também!
print('It is $value'); //Pode usar $ para qualquer variável concatenar!
```

```dart
List<String> listanomes = ['Ricarth', 'Natália', 'Alex', 'Ândriu', 'André'];
```

```dart
List<dynamic> kako = [27, 1.86, true, 'Caio Couto Moreira', 'Kako']; //várias variáveis
```
>obs.: Usar dinamic é custoso para o Dart

```dart
List<dynamic> kako = [idade, altura, geek, nome, apelido]; //posso usar variáveis
```

```dart
const int value = 16; //constante
final int value2; //permite iniciar sem valor mas atribui somente uma vez!

value2 = 18;
```

```dart
var value = 'var';
```

## Funções
```dart
bool funcEstaMadura(int dias){
  if (diasDesdeColheita >= 30 ){
    isMadura = true;
  }else{
    isMadura = false;
  }
}
```

É possível não inserir retorno na função o que o deixa do tipo *void* implicitamente
```dart
void function(){
//
}
```
ou
```dart
function(){
//
}
```

## Parâmetros
### Posicionais Obrigatórios

```dart
mostrarMadura(String nome, int dias){ 
//
}
```

Possível:
```dart
mostrarMadura("Uva", 40);
```

Não possível:
```dart
mostrarMadura(40, "Uva");
```
Em posicionais obrigatórios, a ordem dos parâmetros não pode ser alterada!
### Nomeados Opcionais

```dart
mostrarMadura(String nome, int dias, {String? cor}){ 
//
}
```
Neste caso, *cor* é opcional, mas é obrigado usar o símbolo *?* para deixar a possibilidade de ser nulo.

```dart
mostrarMadura("Uva", 40, cor: "Roxa");
```
É preciso esclarecer qual é o parâmetro!

```dart
mostrarMadura(String nome, {int? dias, String? cor}){ 
//
}
```
É possível usar várias opcionais na mesma chaves!

```dart
mostrarMadura("Uva", dias: 40, cor: "Roxa");
```
ou
```dart
mostrarMadura("Uva", cor: "Roxa", dias: 40);
```
Não importa a ordem nas opcionais!
### Parâmetros "Padrão"

```dart
mostrarMadura(String nome, int dias, {String cor = "Sem cor"}){ 
//
}
```
É possível atribuir um valor padrão ao parâmetro!
### Modificador "required"

```dart
mostrarMadura({required String nome, required int dias, required String cor}){ 
//
}
```
Parâmeros opcionais, mas requeridos. Possível usar em qualquer ordem!

## Classes
```dart
class Fruta {
String nome;
double peso;
String cor;
bool? iSmadura;

Fruta(this.nome, this.peso, this.cor, {this.isMadura});

estaMadura(int diasParaMadura){
    isMadura = diasDesdeColheita >= diasParaMadura;
  }
}
```

## Herança

```dart
class Legumes extends Alimento {

  bool isPrecisaCozinhar;
  
Legumes(String nome,  double peso,  String cor, this.isPrecisaCozinhar) : super(nome, peso, cor);
}
```
O *super* referencia os parâmetros da classe pai!

```dart
Legumes mandioca1 = Legumes('Macaxeira', 1200, 'Marrom', true);
```
## Classe abstrata
```dart
abstract class Bolo {
  void separarIngredientes();

  void fazerMassa();

  void assar();
}
```

```dart
class Legumes extends Alimento implements Bolo{

  bool isPrecisaCozinhar;
  
Legumes(String nome,  double peso,  String cor, this.isPrecisaCozinhar) : super(nome, peso, cor);

  @override
  void assar() {
    // TODO: implement assar
  }
  @override
  void fazerMassa() {
    // TODO: implement fazerMassa
  }
  @override
  void separarIngredientes() {
    // TODO: implement separarIngredientes
  }
}
```

```dart
class Nozes extends Fruta{

//...

  @override
  void fazerMassa() { //Sobrescrevendo a função da classe abstrata que foi herdada!
    print('Tirar a casca');
    super.fazerMassa(); //Chama a função original da classe Pai!
  }
}
```
Nozes precisa tirar a casca!

## Input
```dart
import 'dart:io'

void main(){
String? idade = stdin.readLineSync(); //aguarda escrever algo
print(idade);
}
```

# Flutter
## Instalação
1. Windows Power Shell recente
2. Git Para Windows recente
3. Fazer o download do SDK
>**Aviso:** não instale o Flutter em um caminho que contenha caracteres especiais ou espaços.
**Aviso:** não instale o Flutter em um diretório `C:\Program Files\`que exija privilégios elevados.
4. instalar Android Studio
>Obs.:
![[Pasted image 20231001040059.png]]
Existe a possibilidade da necessidade de instalar esses dois detalhes!
5. Descompactar a pasta do flutter em C:
6. Copiar o caminho da pasta bin dentro da pasta flutter
7. Abrir "Editar Variáveis de Ambiente do Sistema" no Windows
![[Pasted image 20231001104941.png]]
8. Editar *Path*
![[Pasted image 20231001105011.png]]
![[Pasted image 20231001105022.png]]
9. Abrir terminal e rodar: (Para verificar a instalação)
```cmd
flutter doctor
```
![[Pasted image 20231001105128.png]]
10. Aceite as licenças:
```cmd
flutter doctor --android-licenses
```
![[Pasted image 20231001105136.png]]

## Configuração no VSCode
1. Instale o plugin do Flutter no VS Code
2. Em Command Pallet execute Flutter: Run Flutter Doctor

## Criando um projeto
<kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> para abrir Command Pallet
Acesse
Flutter: New Project > Applications > Selecione a pasta
> Antes de renomear o projeto, selecione a engrenagem e aplique as configurações do projeto!

Renomeie o projeto
