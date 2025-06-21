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
<h1>Tratando e filtrando os dados</h1>
<p>
    Como nossos dados serão usados pelo time de ML para criação de um modelo de precificação de imóveis, é importante tratarmos os dados nulos, uma vez que dados nulos não podem ser utilizados no treinamento de modelos de ML.
</p>

<h2>Lidando com dados nulos</h2>
<p>
    Para lidar com os valores nulos usei os seguintes métodos:
    <ol>
        <li><b>isnull():</b> o seguinte método usei com a finalidade de verificar as linhas ou colunas que possuem os valores nulos. Ele retorna um DataFrame com os campos preenchidos com valores <b>Booleanos</b>, isto é, <b>"True"</b> em caso de termos um valor nulo na celula e <b>"False"</b> caso não seja um campo nulo, sendo que o DataFrame é muito grande e não é possível ver todos valores nulos. Usei o seguinte método juntamente com o método <b>sum()</b>, assim consegui o total de nulos em cada coluna.</li>
        <li><b>fillna():</b> o seguinte método foi usado para substituir os campos nulos com zero (0) pois os valores nulos só existiam nas colunas númericas. A abordagem de usar o zero(0) para substituir os valores nulos foi uma escolha, depende da finalidade de cada projecto, poderia ter usado uma outra abordagem como por exemplo, preencher os campus nulos usando a interpolação, etc. Mais para o DataFrame em causa foi pedido que substituissemos por 0.</li>
    </ol>
</p>
<h2>Removendo registros</h2>
<p>
    Foi necessário remover alguns registros do nossa Base de Dados, pois alguns registros existentes na base de dados não fazem muito sentido, por exemplo:
    <ul>
        <li>partamentos que possuem valor de aluguel igual a 0;</li>
        <li>apartamentos com o valor do condomínio igual a 0.</li>
    </ul>
    Esses registros são inconsistentes, por isso devemos removê-los da nossa base de dados.
    Para conseguir acessar as celulas desejadas foi preciso usar o método <b>query()</b> com as devidas condições para acessar os registros desejados, e pegamos os indices dos dados desejados e armazenamos nula variável <b>"remover_registros"</b>. Depois de pegar os devidos indíces usei o método <b>drop()</b>, onde passei como parâmetro o <b>"remover_registros"</b>, o <b>axis=0 (0 para linhas, 1 para colunas)</b> e <b>inplace=True (para fazer as modificações directamente na Base de dados)</b> ficando da seguinte forma o comando: <b>drop(remver_registros, axis=0, inplace=True)</b>
    Removi também a coluna <b>"Tipo"</b> pois possuia somente um valor único, nesse caso o parâmetro <b>axis=1</b>. 
</p>
<h2>Filtros</h2>
<p>
    Para os filtros pedidos usei o método manual, como também o método <b>query()</b> de forma resumida.
    Os filtros pedidos:
    <ol>
        <li>Apartamentos com 1 quarto e aluguel < R$ 1200</li>
        <li>Apartamentos com 2 quartos, aluguel < R$ 3000 e área > 70 metros quadrados</li>
    </ol>
</p>
<h2>Salvando os dados</h2>
<p>
    Finalmente para salvar os dados usei o método to_csv() para salvar a Base de dados com as remoções e os dados nulos tratados, pronta para entregar ao grupo de ML criar o modelo de previsão de preços de imóveis.

    O método to_csv() possui alguns parâmetros que é necessário destacar:
    Primeiro é o nome do documento segundo colocamos o index=False para não armazenar com os inices e podemos usar o "sep='tipo de separador'"

</p>
