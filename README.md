![INFOS](https://github.com/user-attachments/assets/fbe1e4e8-31da-4b31-be6f-2d97107edad5)

<h1>Welcome</h1>
<p>Esse é o meu projecto introdutório utilizando a biblioteca <strong>Pandas</strong> para análisar dados de aluguer de imóveis.<br>Temos as seguintes tarefas a serem realizadas com <strong>DataFrame</strong>:<br>
<ul>
    <li>Importar os dados;</li>
    <li>Verificar as características gerais da base de dados;</li>
    <li>Análise exploratória de dados;</li>
    <li>
        Tratando e filtrando os dados
        <ul>
            <li>Lidando com dados nulos;</li>
            <li>Removendo registros;</li>
            <li>Filtros;</li>
            <li>Salvando os dados.</li>
        </ul>       
    </li>
    <li>Manipulando os dados.</li>
</ul>
</p>
<h1>Pandas</h1>
<p>Trata-se de uma biblioteca para análise de dados em Python, que possui diversos recursos para trabalharmos com dados. Com ela, podemos limpar, manipular, analisar e visualizar os dados.</p>
<h1>Importar os dados</h1>
<p>Para importar os dados precisarei:<br>
    <ol>
        <li>Importar a biblioteca Pandas;</li>
        <li>Usar o método <strong>read_csv()</strong> para ler a informação que está num ficheiro <b>.csv</b>;</li>
        <li>Guardar o <strong>DataFrame</strong> numa variável.</li>
    </ol>
</p>
<h1>Verificar as características gerais da base de dados</h1>
<p>Para verificar as características gerais da Base de dados usei o método <strong>info()</strong> que me retornou o tipo de dado de cada coluna.</p>
<h1>Análise exploratória de dados</h1>
<p>
    O processo de <b>Análise exploratória de dados(EDA)</b> consiste em buscar entender como são estruturados os dados que queremos analisar<br>
    É um processo de caráter <b>investigativo</b>, onde tentamos compreender várias características como: os valores presentes nas colunas, os tipos de estrutura de dados, verificar se são dados qualitativos ou quantitativos, se há valores faltantes ou incomuns.<br>
    Algumas perguntas que podemos fazer nesse momento são:
    <ol>
        <li>Quais os valores médios de aluguel por tipo de imóvel?</li>
        <li>Qual o percentual de cada tipo de imóvel na nossa base de dados?</li>
    </ol>
</p>
<h1>Quais os valores médios de aluguel por tipo de imóvel?</h1>
<p>
    Para responder a essa questão usei o método <b>groupby()</b> juntamente com o método <b>mean()</b> para poder calcular a média de aluguel por tipo de imóvel.
</p>
<h2>groupby()</h2>
<p>
    O método <b>groupby()</b> do Pandas permite agrupar e resumir dados de um DataFrame, com base em um ou mais critérios. Esses critérios podem ser variáveis numéricas ou categóricas, como colunas ou índices do DataFrame.<br>
    O método <b>groupby()</b> funciona em conjunto com outras funções do Pandas, como a <b>sum de soma ou a mean que é a média.</b>Com essas funções, podemos fazer agregações conforme o agrupamento que realizamos.
</p>
<h1>Qual o percentual de cada tipo de imóvel na nossa base de dados?</h1>
<p>
  Nesse ponto, precisamos descobrir quais tipos de imóveis estão mais ou menos presentes na nossa base de dados.
  Para responder essa questão usei os seguintes métodos:
  <ul>
    <li><b>unique()</b>: para pegar os valores unicos na base de dados.</li>
    <li><b>value_counts(normalize=True)</b>: Conta quantas vezes cada um desses tipos aparecem na nossa base de dados. O parâmetro "normalize=True" permite que o método value_counts() nos retorne a quantidade em percentuais.</li>
  </ul><br>
    E no final criei um gráfico para uma melhor visualização com o método <b>plot()</b>. 
</p>
