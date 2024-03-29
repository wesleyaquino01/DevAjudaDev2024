# "Hello World!"

```cs

namespace HelloWorld;

 internal class Program
 {
     static void Main(string[] args)
     {
         Console.WriteLine("Hello, World!");
     }
 }
```

# Pacotes 

### Nuget

>NuGet é um gerenciador de pacotes usado principalmente para empacotar e distribuir software escrito em .NET e na estrutura .NET.

    dotnet nuget push
    dotnet nuget delete
    dotnet nuget list source 

# .NET CLI

> O que é CLI? De uma forma simples, a sigla significa Interface de Linha de Comando. Ele é um programa que permite que os usuários digitem comandos de texto dando instruções a um computador para fazer funções específicas.



```cs
    dotnet new- Cria um novo projeto, arquivo de configuração ou solução com base no modelo especificado.

    dotnet new <TEMPLATE> [--dry-run] [--force] [-lang|--language {"C#"|"F#"|VB}]
    [-n|--name <OUTPUT_NAME>] [-f|--framework <FRAMEWORK>] [--no-update-check]
    [-o|--output <OUTPUT_DIRECTORY>] [--project <PROJECT_PATH>]
    [-d|--diagnostics] [--verbosity <LEVEL>] [Template options]

    dotnet watch [<command>]
        [--list]
    [--no-hot-reload] [--non-interactive]
    [--project <PROJECT>]
    [-q|--quiet] [-v|--verbose]
    [--version]
    [--] <forwarded arguments> 

    dotnet watch -?|-h|--help

    dotnet --info

    dotnet new install- instala um pacote de modelos.

    dotnet new uninstall- desinstala um pacote de modelo.

    dotnet new update- atualiza pacotes de modelos instalados.

    dotnet run - Executa o código-fonte sem nenhum comando explícito de compilação ou inicialização.
```

# Extensão 

    .cs ou .vb

## Testes

Método TDD
Testes unitários e de testes de integração
Testes de ponta a ponta (E2E)

![alt text](image.png)

```cs
namespace StringLibraryTest;

[TestClass]
public class UnitTest1
{
    [TestMethod]
    public void TestMethod1()
    {
    }
}
```

```cs

using UtilityLibraries;

namespace StringLibraryTest
{
    [TestClass]
    public class UnitTest1
    {
        [TestMethod]
        public void TestStartsWithUpper()
        {
            // Tests that we expect to return true.
            string[] words = { "Alphabet", "Zebra", "ABC", "Αθήνα", "Москва" };
            foreach (var word in words)
            {
                bool result = word.StartsWithUpper();
                Assert.IsTrue(result,
                       string.Format("Expected for '{0}': true; Actual: {1}",
                                     word, result));
            }
        }

        [TestMethod]
        public void TestDoesNotStartWithUpper()
        {
            // Tests that we expect to return false.
            string[] words = { "alphabet", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                               "1234", ".", ";", " " };
            foreach (var word in words)
            {
                bool result = word.StartsWithUpper();
                Assert.IsFalse(result,
                       string.Format("Expected for '{0}': false; Actual: {1}",
                                     word, result));
            }
        }

        [TestMethod]
        public void DirectCallWithNullOrEmpty()
        {
            // Tests that we expect to return false.
            string?[] words = { string.Empty, null };
            foreach (var word in words)
            {
                bool result = StringLibrary.StartsWithUpper(word);
                Assert.IsFalse(result,
                       string.Format("Expected for '{0}': false; Actual: {1}",
                                     word == null ? "<null>" : word, result));
            }
        }
    }
}

```


# Modificadores de acesso 

![alt text](image.png)

    Pra começar existem somente 3 modificadores (private, protected e public), e com isso temos 4 níveis de visibilidade

    Os níveis são os que você disse: private, default, protected e public

    Private: A única classe que tem acesso ao atributo é a própria classe que o define, ou seja, se uma classe Pessoa declara um atributo privado chamado nome, somente a classe Pessoa terá acesso a ele.

    Default: Tem acesso a um atributo default (identificado pela ausência de modificadores) todas as classes que estiverem no mesmo pacote que a classe que possui o atributo.

    Protected: Esse é o que pega mais gente, ele é praticamente igual ao default, com a diferença de que se uma classe (mesmo que esteja fora do pacote) estende da classe com o atributo protected, ela terá acesso a ele. Então o acesso é por pacote e por herança.

    Public: Esse é fácil, todos tem acesso :)

    O nível de visibilidade envolve encapsulamento. É sempre dito como boa prática que atributos internos devem ser privados, pois classes externas nem devem saber que ele existe. O que a classe expõe são suas funcionalidades, sua API, se preferir. Expor atributos internos pode causar sérios problemas de segurança. Se tem algo que é inerente à implementação, que pode vir a mudar no futuro. provavelmente deve ser privado.



```cs
    class Animal {
  protected void metodoProtected() {
    System.out.println("animal protected");
  }
  private void metodoPrivate() {
    System.out.println("animal private");
  }
}

class Gato extends Animal {
  protected void metodoProtected() {
    System.out.println("gato protected");
  }
  private void metodoPrivate() {
    System.out.println("gato private");
  }
}

```
Agora, se você tiver uma referência do tipo Animal para um objeto do tipo Gato, e chamar:


```cs
Animal animal = new Gato();
animal.metodoProtected();
animal.metodoPrivate();
```
O resultado será
gato protected
animal private
