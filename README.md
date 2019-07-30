# Prova de Java

## Considerações iniciais

1. **Tempo estimado para solução: 2h** (o tempo será medido entre o primeiro e o último commit)
2. Faça um **fork** deste repositório, resolva localmente e ao final submeta um **pull request** para avaliação.
3. Necessários conhecimentos básicos de modelagem UML

## Problema 01 - Ler e atualizar um arquivo XML

Dado o arquivo XML com os dados dos alunos `alunos.xml`:

```xml
<root>
	<resumo>
		<media_geral>0.0</media_geral>
		<nota_maxima>0.0</nota_maxima>
		<nota_minima>0.0</nota_minima>
		<quantidade_alunos>0</quantidade_alunos>
	</resumo>
	<alunos>
		<aluno id="21" nome="João" media="7.5" />
		<aluno id="22" nome="Pedro" media="8.2" />
		<aluno id="23" nome="Okio" media="9.5" />
		<aluno id="44" nome="Francisco" media="9.1" />
		<aluno id="18" nome="Joaquim" media="7.2" />
	</alunos>
</root>
```

Crir um programa em Java para realizar os seguintes procedimentos:

1. Ler o arquivo `alunos.xml`
2. Calcular e atualizar os valores em `resumo`
3. Salvar backup do arquivo original como `alunos.xml.bak`
4. Sobrescrever arquivo atualizado `alunos.xml`
5. Imprimir uma tabela na tela com alunos ordenados pelo id

Saída esperada no item 5:

```
ID    Nome           Média
--------------------------
18    Joaquim         7.2
21    João            7.5
22    Pedro           8.2
23    Okio            9.5
44    Francisco       9.1
--------------------------
Média geral           8.3
```

* Atenção ao alinhamento das colunas
* Atenção ao formato dos número

## Sugestão para implementação

No arquivo `Problema01.java` há uma sugestão para implementação.

```java
String filename = "alunos.xml";
backup( filename, filename + ".bak" );
MeuContainerEscolhido alunos = lerAlunosDoArquivoXml( filename );
float mediaGeral = calcularMediaGeral( alunos );
float notaMaxima = calcularNotaMaxima( alunos );
float notaMinima = calcularNotaMinima( alunos );
int quantidadeDeAlunos = calcularQuantidadeDeAlunos( alunos );
atualizarResumo( filename, mediaGeral, notaMinima, notaMaxima, quantidadeDeAlunos );
imprimirTabelaDeAlunos( alunos );
```

## Diagramas UML

Criar diagramas UML de classe, atividade e sequência para o projeto e substituir as imagens na pasta `img`.

## Diagrama de classe

Substituir a imagem abaixo pelo diagrama correspondente.

![Diagrama de classe](img/diagrama_de_classe.png)

## Diagrama de atividade

Substituir a imagem abaixo pelo diagrama correspondente.

![Diagrama de atividade](img/diagrama_de_atividade.png)

## Diagrama de sequência

Substituir a imagem abaixo pelo diagrama correspondente.

![Diagrama de sequencia](img/diagrama_de_sequencia.png)

## Considerações finais

1. Criar uma classe `Aluno` com atributos privados e funções de acesso get/set para cada variável.

2. Para cada variável a atualizar no grupo resumo crie uma função especializada
recebendo como único parâmetro a coleção de alunos e retornando o valor
correspondente.

3. Inclua tratamento de exceção para todos os casos que achar pertinente (por exemplo,
número de alunos igual a zero no cálculo da média).

4. Criar as rotinas teste e indicar como executar os teste.
Usar JUnit ou qualquer outro framework de teste de sua preferência, o importante é ter como testar as funções.

5. Criar um script `compilar.sh` (Unix/Linux) ou `compilar.bat` (Windows) para criação do executável.

5. Criar um script `executar_teste.sh` (Unix/Linux) ou `executar_teste.bat` (Windows) para testar o executável.

7. Comentar extensivamente o código indicando por que tal abordagem foi escolhida, isto me ajudará a entender suas decisões.
Por exemplo, "escolhi como container *Vector* em vem de *List* pois me traz a seguinte vantagem..."

8. Os commits devem ser curtos (com o máximo 30 linhas), com foco único e com mensagem de log descritiva.

**Boa sorte**
