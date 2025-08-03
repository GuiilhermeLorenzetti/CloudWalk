# CloudWalk

# Database  

Scrips e mais informações -> link 

Estrutura: 

Minha ideia aqui foi montar uma arquitetura onde:

Bronze: É o próprio arquivo CSV recebido, que permanece armazenado como fonte original.

Silver: O mesmo conteúdo do CSV (1:1 em relação à camada Bronze), mas agora inserido dentro do banco de dados.

Gold: Tabelas tratadas e estruturadas para serem utilizadas no dashboard.

Por se tratar de um arquivo pequeno, não houve necessidade de normalização completa no Power BI, nem de criação formal de tabelas fato e dimensão. Optei por seguir dessa forma para demonstrar o caminho que seria adotado com arquivos maiores e mais complexos no dia a dia.

Portanto, o arquivo enviado passa por tratamento e normalização na transição da camada Silver para a Gold. Apenas as tabelas da camada Gold são utilizadas no dashboard, aplicando regras de negócio relevantes. A camada Silver é tratada como a fonte de verdade, podendo ser reutilizada em outros projetos.

