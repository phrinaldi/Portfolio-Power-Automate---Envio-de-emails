# Portfolio-Power-Automate---Envio-de-emails

# Case:
Todo início de Mês o time de Pricing envia por e-mail uma planilha chamada “Tabela de Preços_Nomedomes”.xlsx com as atualizações dos preços dos Produtos de cada negócio e vendedor.
Os analistas dos times de Marketing Estratégico precisam baixar essa planilha e copiar as novas informações referentes ao seu negócio, atualizar a lista do Sharepoint, salvar o arquivo enviado numa pasta de Backup, na subpasta referente ao ano de envio do arquivo.

Ex:
Em Dezembro de 2023:

Backup>2023

Em Janeiro de 2024:

Backup>2024
 
Após a atualização da lista do SP é necessário enviar um e-mail para os Vendedores, informando que a Tabela de Preços foi atualizada. Nesse e-mail é necessário ter uma Tabela, com a lista dos produtos que cada pessoa é responsável pela venda e o seu novo preço.

Hoje esse processo é feito de forma totalmente manual e leva em torno de 3 horas. 

Uma  de suas primeiras atividades na empresa é automatizar esse fluxo de alguma forma. 

Felizmente você é detentor de conhecimento da ferramenta Power Automate e sabe que é possível automatizar essa tarefa e reduzir drasticamente o tempo de sua execução.

# Fluxo resumido

Etapas:
1- Receber o email

2- Baixar o arquivo

3- Salvar arquivo numa pasta backup

4- Pegar a tabela desse arquivo 

5- Montar e enviar o email

5- Copiar os dados para as respectivas listas

# Fluxo Envio do email até arquivo backup

Iniciar quando receber um novo email

1- Criar um novo fluxo da Nuvem

2- Quando um novo email é recebido

2.1- Tem no assunto Tabela de Preços

3- Pegar o anexo do email 

4- Criar uma condição para ver se o anexo é excel ou word

5- Se for Excel, criar um arquivo com o conteúdo desse anexo

6- Salvar e Testar (clicar em testar e aí enviar um email com anexo)

# Fluxo do arquivo no backup até o envio do email

1- Criar um novo fluxo da Nuvem

2- Quando um arquivo é criado na pasta backup do One Drive

3- Obter tabelas desse arquivo

4- Listar as linhas da tabela de acordo com o Negócio – FILTRAR LINHAS

4.1- Compor - nome do endereço do arquivo

4.2- Tabela - nome da tabela

4.2- Consulta de Filtro - Negócio eq 'Agro’


FILTRAR AS COLUNAS:
5- Depois de listar as linhas, Selecionar o que eu quero na tabela: Selecionar

5.1- Value (valores de cada linha)

5.2- Mapa: Produto – EXPRESSÃO – item()[‘Produto’]


6- Criar Tabela HTML – saída do Selecionar


7- Enviar email

8- Pegou as linhas de cada ‘tabela’ e colocou no Lists

9- Colocar o filtro em um Escopo

10- copiar o escopo e colar, alterando o filtro
