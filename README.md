# 24/10/2024 - PYTHON POO - DAY 1

### 1. APRESENTAÇÃO
- Iremos verificar nesse modulo o que são escopos e namespaces.

### 2. ESCOPO E NAMESPACES

Em Python, escopos e namespaces são conceitos fundamentais para a organização e gerenciamento de variáveis e nomes dentro do código.

- **Escopo** refere-se ao contexto no qual uma variável é acessível. Existem quatro níveis principais de escopo em Python:

    1. **Local:**  
       Variáveis definidas dentro de uma função, acessíveis apenas dentro dessa função.

    2. **Enclosing:**  
       Variáveis em funções envolventes, ou seja, em uma função dentro de outra (não na função principal).

    3. **Global:**  
       Variáveis definidas no nível do módulo, acessíveis em qualquer lugar dentro do módulo.

    4. **Built-in:**  
       Variáveis e funções incorporadas ao Python, como `len()` ou `print()`.

- **Namespace** é uma coleção de nomes mapeados para objetos. Cada escopo tem seu próprio namespace.  
  Em outras palavras, é como um dicionário onde os nomes das variáveis são as chaves, e os valores são os objetos a que esses nomes se referem.

Esses conceitos ajudam a evitar conflitos de nome e permitem que o Python organize o acesso e a modificação de variáveis de forma eficiente e segura.

**Importando funções**

```python

    import math
    
    print(math.pow(2, 2))
    print(math.factorial(5))
    print(math.log(4, 2))
    print(math.cos(180))

```
# 25/10/2024 - PYTHON POO - DAY 2

### 3. APRESENTAÇÃO
- Iremos verificar nesse modulo o que são classes e objetos.

### 4. CLASSES E OBJETO – CRIANDO UMA CLASSE

Em Python, classes e objetos são os principais conceitos da programação orientada a objetos (OOP).

- **Classe** é um modelo ou "blueprint" que define a estrutura e o comportamento de um conjunto de objetos.  
  Uma classe especifica os atributos (dados) e métodos (funções) que os objetos criados a partir dela terão.  
  Pense em uma classe como um plano para construir algo, como uma planta de uma casa.

    ```python
    class Car:
        def __init__(self, make, model, year):
            self.make = make
            self.model = model
            self.year = year
      
        def start_engine(self):
            print(f"{self.make} {self.model} iniciado!")
    ```

    Neste exemplo, `Car` é uma classe que define um carro com atributos como `make`, `model`, e `year`, e um método `start_engine()`.

- **Objeto** é uma instância de uma classe.  
  Quando você cria um objeto a partir de uma classe, esse objeto tem as propriedades e comportamentos definidos pela classe.  

    Cada objeto pode ter valores diferentes para seus atributos, mas todos compartilham a mesma estrutura definida pela classe.

    ```python
    my_car = Car("Toyota", "Corolla", 2021)
    my_car.start_engine()  # Saída: Toyota Corolla iniciado!
    ```

    Aqui, `my_car` é um objeto da classe `Car`. Ele possui os valores "Toyota", "Corolla", e 2021 para os atributos `make`, `model`, e `year`, respectivamente.

Em resumo, classes são modelos que definem a estrutura e comportamento dos objetos, enquanto objetos são instâncias concretas dessas classes, com atributos específicos e a capacidade de executar métodos definidos na classe.

# 26/10/2024 - PYTHON POO - DAY 3

### 5. CLASSES E OBJETO – DEFININDO OS ATRIBUTOS

- **Atributos:** São as variáveis definidas dentro de uma classe que armazenam o estado ou as características de um objeto. Cada objeto de uma classe pode ter valores diferentes para seus atributos, mas todos compartilham a mesma estrutura.

Exemplo:

- Crie um arquivo `carro.py` e insira o código abaixo:

    ```python
    class Carro:
        def __init__(self, cor, qtd_portas, tipo_combustivel, potencia):
            self.cor = cor
            self.qtd_portas = qtd_portas
            self.tipo_combustivel = tipo_combustivel
            self.potencia = potencia
    ```

Em Python, `__init__` e `self` são elementos essenciais para trabalhar com classes e objetos.

- **`__init__`:**
    - O método `__init__` é um método especial em Python conhecido como o construtor da classe.  
      Ele é automaticamente chamado quando um novo objeto é criado a partir de uma classe.
    - Seu principal propósito é inicializar os atributos do objeto com valores fornecidos quando o objeto é criado.

    Por exemplo:

    ```python
    class Car:
        def __init__(self, make, model, year):
            self.make = make
            self.model = model
            self.year = year
    ```

    Neste exemplo, `__init__` recebe três parâmetros além de `self` (`make`, `model`, `year`) e usa esses parâmetros para inicializar os atributos `make`, `model`, e `year` do objeto.

- **`self`:**
    - `self` é uma referência ao próprio objeto que está sendo criado ou manipulado.  
      Ele é sempre o primeiro parâmetro de qualquer método dentro de uma classe e permite acessar os atributos e métodos da instância.
    - Quando você chama um método em um objeto, o Python automaticamExemplo:

- Crie um arquivo `carro.py` e insira o código abaixo:

    ```python
    class Carro:
        def __init__(self, cor, qtd_portas, tipo_combustivel, potencia):
            self.cor = cor
            self.qtd_portas = qtd_portas
            self.tipo_combustivel = tipo_combustivel
            self.potencia = potencia
    ```
    ```python
    class Car:
        def __init__(self, make, model, year):
            self.make = make  # `self.make` refere-se ao atributo do objeto
            self.model = model
            self.year = year

        def start_engine(self):
            print(f"{self.make} {self.model} engine started!")  # Usa `self` para acessar o atributo do objeto
    ```

    Aqui, `self.make`, `self.model`, e `self.year` referem-se aos atributos do objeto que está sendo criado. Quando você chama `start_engine()`, ele acessa `self.make` e `self.model` para personalizar a mensagem.

Resumindo:

- **`__init__`:** Método especial usado para inicializar um objeto ao criá-lo.
- **`self`:** Referência ao próprio objeto, permitindo acessar e modificar seus atributos e métodos dentro das definições de classe.

### 6. CLASSES E OBJETO – DEFININDO METODOS

- **Métodos:** Em programação orientada a objetos, métodos são funções definidas dentro de uma classe que descrevem os comportamentos que os objetos dessa classe podem executar. Eles podem modificar o estado do objeto, interagir com outros objetos ou realizar operações específicas.

Exemplo:

- Crie um arquivo `carro.py` e insira o código abaixo:

    ```python
    class Carro:
        def __init__(self, cor, qtd_portas, tipo_combustivel, potencia, qtd_combustivel, is_ligado):
            self.cor = cor
            self.qtd_portas = qtd_portas
            self.tipo_combustivel = tipo_combustivel
            self.potencia = potencia
            self.qtd_combustivel = qtd_combustivel
            self.is_ligado = is_ligado
        
        # Metodos

        def abastecer(self):
            self.qtd_combustivel += 20

        def ligar(self):
            if self.is_ligado:
                print("O carro ja esta ligado")
            else:
                self.is_ligado == True

        def desligar(self):
            if self.is_ligado == False:
                print("O carro ja esta desligado")
            else:
                self.is_ligado == False        
    ```




