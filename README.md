![Prosperidade](https://github.com/user-attachments/assets/7d0d9418-b266-46da-9e3f-e13c6c6788c2)
# Simulador de investimento em FIIs / curso Santander - Excel com Inteligência Artificial
## Etapas da criação:
1. Essa é uma das atividade do Curso "Santander - Excel com Inteligência Artificial", ofertado pela Santander Open Academy (https://www.santanderopenacademy.com/pt_br/index.html) e disponibilizado na plataforma da DIO (https://dio.me/).
2. A pasta de trabalho foi criada seguindo as orientações do professor Felipe da DIO.
3. Foi utilizado o software Microsoft Excel.
4. São duas abas (planilhas), sendo uma nomeada "APP", onde o usuário vai inserir os dados e a planilha nomeada "parâmetros", onde estão informações úteis para algumas fómulas e células que contenham a seleção de dados.
5. As células com fórmulas e textos foram bloqueadas para evitar que sejam deletadas acidentalmente.
6. Algumas células e tabelas de apoio foram nomeadas com textos específicos, como exemplo a célula E14 foi nomeada como "Taxa_rendimento_mensal", usando o conceito da aula de intervalos nomeados.
   
## Como usar:
Abra a pasta de trabalho "Prosperidade" em seu Microsoft Excel. Existem duas abas (planilhas) para você usar, nomeadas como "APP" e "Parâmetros".
## Aba (planilha) APP:
### Informações básicas:
![Captura de tela 2025-06-08 095848](https://github.com/user-attachments/assets/3c0ff326-6ec4-432d-95ea-a852663c568d)

As céluas pintadas em verde claro são as que permitem edição, onde você vai inserir os dados necessários.
1. Renda mensal: é quanto você recebe mensalmente (salário, aluguéis, mesada, etc).
2. Rendimento da carteira: é o percentual de quanto os seus investimentos rendem todo mês. Esse valor você pode estimar ou calcular (exemplo um fundo imobiliário está pagando 0,78% de renda).
3. Automaticamente a planilha calcula o valor da sugestão de investimento mensal (30%), que segundo especialistas seria o ideal. Fórmula usada =$E$7*30%, é a multiplicação da renda mensal (digitada na cálula E7, que foi travada com $) pelo percentual sugerido.

### Investimento mensal:
![Captura de tela 2025-06-08 100624](https://github.com/user-attachments/assets/2f0fc6e1-9577-44ab-b15a-2e3713b318a8)

As células pintadas em verde claro são as que permitem edição, onde você vai inserir os dados necessários.
1. Quanto investir por mês: você escolhe. Pode ser o valor sugerido (30% da tabela informações básicas) ou outro valor que você considere ser possível investir.
2. Por quantos anos: período de tempo que você investirá.
3. Taxa de rendimento mensal: é quanto você espera que seus investimentos renderão todos os meses.
4. Patrimônio acumulado: esse campo é calculado automaticamente, usando a fórmula =VF(Taxa_rendimento_mensal;Prazo_investimento * 12;Investimento_mensal * -1). Se você investir todos os meses, durante o período em anos previsto e a taxa de rendimento se mantiver, o patrimônio acumulado será aquele valor.
5. Dividendos mensais: os fundos imobiliários tem a característica de pagar dividendos, que seria como um aluguel, todo mês. Ele é calculado com base no teu patrimônio acumulado vezes o rendimento da carteira da tabela informações básicas. A fórmula é =Patrimonio*Rendimento_carteira
#### Projeção - Patrimônio - Dividendo:
Essa tabela é preenhida automaticamente com os dados que voê digitar na tabela Investimento mensal. É a projeção (estimativa) de quanto seria o patrimônio acumulado em determinados períodos de tempo (1 a 30 anos) e quanto o patrimônio irá gerar de dividendos.
Fórmula do patrimônio é "=VF(Taxa_rendimento_mensal;B19 * 12;Investimento_mensal * -1)"
Fórmula dos dividendos mensais é =D19*Rendimento_carteira
São sete linhas de projeções pré determinadas. A fórmula é arrastada a partir da linha 19 até a 25, tanto na coluna Patrimônio quanto na coluna Dividendos.
Importante: os cálculos são uma estimativa, pois as taxas de rendimento dos investimentos podem variar, tanto para mais quanto para menos. Por isso é importe sempre acompanhar e estudar o assunto.

### Perfil de Investidor:
![Captura de tela 2025-06-08 114218](https://github.com/user-attachments/assets/a7090b39-7259-4a8c-bd85-d612863624fb)

1. Na célula que contém o ícone de um filtro, selecione o perfil de investidor.
2. Existem três perfis básicos de investidor: Conservador, Moderado e Agressivo (pesquise em sites de investimento e você entenderá cada).
3. Para a seleção do perfir usei o menu "Dados" do Excel e lista de dados. Usei uma fórmula que busca os dados na planilha "Parâmetros", nessa aba há uma tabela nomeada "perfil_investidor" onde você pode inserir novos perfis de investidor, se um dia for necessário. Como exemplo eu inseri a palavra "teste" como um novo ferfil de investidor.
4. Escolhendo um dos três perfis, a cor da fonte vai alterar automaticamente (por exemplo, a cor do agressivo é vermelho), usando a formatação condicional explicada em uma das aulas. Além do detalhe da cor da fonte, abaixo aparecerá uma tabela com os percentuais sugeridos de cadda tipo de FII você deveria comprar.
5. Para retornar o % sugerido utilizei a fómula =PROCV($E$27&"-"&$C29;Tabela_chave;4;0), ela combina o perfil selecionado com o tipo de fundo à esquerda na tabela como o valor a ser procurado na matriz (que é uma tabela de apoio na aba parâmetros), retornando o quarto valor e numa correspondência exata. Veja o exemplo abaixo:

![Captura de tela 2025-06-08 114058](https://github.com/user-attachments/assets/2f697843-e46a-4c6a-828a-1e891a36391b)

1. Já o campo "valores" é calculado pela fòrmula =Investimento_mensal*D29. Que é quanto você pretende investir mensalmente (aquele valor que voê digitou na célula E12 (nomeada como "Investimento_mensal") vezes o percentual sugerido para o tipo de FII baseado no seu perfil de investidor.
2. O total investido será a soma de todos os valores investidos em cada fundo. E esse total será igual ao que você estabelecer na E12 (Investimento_mensal).
3. A cor das linhas da tabela mudam de acordo com o perfil do investidor. Fiz essa experiência para exercitar a formatação condicional.
4. Ao final da aba APP aparece um gráfico par ilustar os valores comprados de cada tipo de FII:
![Captura de tela 2025-06-08 120451](https://github.com/user-attachments/assets/7cfff272-d3cd-4eda-b319-15402c464e1e)

## Aba (planilha) Parâmetros:
1. São duas tabelas nomeadas que servem de apoio à lista de dados do perfil do investidor na aba "APP" e a segunda que é uma tabela para os tipos de FIIs e seus percentuais por tipo de perfil de investidor.
2. Na primeira tabela (nomeada como tabela1) estão os três perfis estabecidos, conforme a aula. Inclui a lista de dados do perfil do investidor da aba "APP" a partir desta tabela, usando uma fórmula na validação de dados. Assim novos perfis podem ser adicionados facilmente, como exemplo inseri o "teste" e esses dados irão automaticamente para a lista do validação de dados;
![Captura de tela 2025-06-08 143356](https://github.com/user-attachments/assets/30189573-4c5f-4879-b2c8-ed53e505a4af)
3. A segunda tabela foi nomeada como "Tabela_chave". Consiste em um primeira coluna que é ocultada e nesta coluna está a fórmula =CONCAT(D4;"-";E4), que concatena as informações de Perfil e Tipo de FII, que estão nas colunas D e E. Já a coluna F é para digitar os percentuais de cada tipo de FII recomendado para determinado tipo de perfil. A chave composta torna os valores únicos e eles que serão procurados pela fórmula =PROCV($E$27&"-"&$C29;Tabela_chave;4;0), utilizada na tabela onde se escolhe o tipo de investidor na aba "APP".
4. Abaixo está a figura da Tabela_chave com a coluna C visível e a fórmula concatenar:
![Captura de tela 2025-06-08 145333](https://github.com/user-attachments/assets/0a465ee4-0c71-4b8e-a6e1-89913728b907)
5. Abaixo está a mesma tabela, porém com a coluna C oculta. Você poderá digitar novos perfis (só lembrando que o nome digitado do novo perfil deverá ser digitado na Tabela1), o tipo de FII e o percentual. Como exemplo digitei 6 linhas para o perfil "Teste" e uma para o perfil "Teste2" que apareceram abaixo do perfil agressivo.
![Captura de tela 2025-06-08 145811](https://github.com/user-attachments/assets/54fc1e22-5503-44af-8666-e2a5068b87b3)

## Considerações finais:
Em caso de dúvida ou se algum erro aparecer na pasta de trabalho, estarei a disposição para ajudar.
