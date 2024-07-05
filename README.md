<p align="center">
  <br>
  <img alt="TerraQ logo" width="150" src="https://sigma01.nyc3.digitaloceanspaces.com/terraq/assets/images/logo/logo.png"/>
  <br>
</p>
 
Repositório contendo as instruções do processo seletivo para desenvolvedor frontend na TerraQ em Jul/24.

# Descrição e objetivos

Este repositório contém uma aplicação simples contendo uma página de mapa e outra página de gráficos.

O principal objetivo deste teste é permitir que você demonstre suas habilidades ao lidar com as bibliotecas [Leaflet](https://github.com/Leaflet/Leaflet) e [ChartJS](https://www.chartjs.org/docs/latest/getting-started/) para a criação de mapas e gráficos, respectivamente.

Na aplicação, há apenas três rotas a serem trabalhadas, sendo elas:
* **"/"** - Página inicial, contendo alguns cartões que levam para as rotas de "/mapa" e "/grafico";

* **"/mapa"** - Página contendo um mapa simples, com um componente de coordenadas do mouse, um componente de escala do mapa, um componente de context menu (ao clicar com o botão direito em qualquer local do mapa);

* **"/grafico"** - Página contendo dados fictícios de dois datasets, um de precipitação (chuva) e outro de temperatura.


# Avaliação
## Lista de tarefas a serem cumpridas
- [ ] Altere o layout da página inicial na rota "/" para exibir apenas dois cartões, onde ambos devem levar para as 2 rotas de: "/mapa" e "/grafico".
- [ ] Na rota "/mapa", alterar o estilo do componente de coordenadas do mouse para que ele fique fixo no canto inferior esquerdo da tela (levando a barra de escala para a direita) e que ele fique com uma fonte maior, contendo um fundo branco com opacidade de 0.5.
- [ ] Na rota "/mapa", alterar o estilo do componente de context menu (popup) de modo que ele tenha um maior espaçamento entre as coordenadas de latitude e longitude.
- [ ] Na rota "/mapa", alterar o texto do componente de context menu (popup) de modo que além da latitude e longitude, ele também exiba a data/hora em que o usuário clicou com o botão direito no mapa. Formato: "DD/MM/YYYY HH:mm:ss". Adicionar também um ícone de calendário ao lado da data/hora.
- [ ] Na rota "/mapa", adicione um botão flutuante no topo, à esquerda da tela, com um ícone de "zoom in" que você preferir, e que ao ser clicado, deve executar a função ZoomInOut('in') que já existe no código fornecido. Faça um ícone logo abaixo que faça a função ZoomInOut('out') ao ser clicado.
- [ ] Na rota "/grafico", adicione um gráfico do ChartJS que contenha os dados de temperatura e precipitação. Adicionar também um botão para alternar entre os datasets de temperatura e precipitação ou visualizar ambos datasets ao mesmo tempo.
- [ ] Altere o tipo de gráfico de precipitação para um gráfico de barras e o tipo de gráfico de temperatura para um gráfico de linhas.
- [ ] Adicionar documentação às funções originais do repositório que não tiverem nenhum tipo de docstring.
- [ ] Comentários explicando novas funcionalidades desenvolvidas e códigos adicionados.
- [ ] Crie um botão que altere o mapa de fundo, utilizando a função já existente "ToggleRaster". Ao clicar neste botão, a imagem de satélite (Google Satélite) deve ser alterada para a imagem de mapa de ruas (OpenStreetMap) e vice-versa (As informações para fazer esta alteração estão no arquivo de rotas web.php).
- [ ] Adicione casos de teste (utilizando cypress) para todas as novas funcionalidades criadas.
- [ ] Crie navegação contínua, ou seja, elementos/botões que permitam ao usuário navegar de uma tela para a outra sem precisar voltar para a tela inicial.
- [ ] Refatore o arquivo ./routes/web.php para que utilize as melhores práticas laravel.
- [ ] Efetue a migração das informações hard-coded de ./routes/web.php para o banco de dados e efetue consultas para retornar os dados.
- [ ] Utilize PEST para escrever testes para essas funcionalidades.


## Critérios avaliados
* Cumprimento do checklist das funcionalidades esperadas;
* Clareza do código;
* Boas práticas e escrita nas mensagens de commits realizados;
* Facilidade de manutenção e extensão das novas funções implementadas;
* Criatividade no consumo das informações entregues;
* Boas práticas em UI/UX;
* Uso do arquivo app.css para estilização dos componentes.

# Dicas
* Os nomes de variáveis e comentários no código podem ser feitos em português ou inglês;
* Se o código submetido demandar instalações de quaisquer natureza, espera-se que hajam instruções de instalação no README;
* Neste teste não há pegadinhas ou detalhes escondidos, então não se preocupe em tentar procurá-los.

# Submissão
* Faça uma cópia do repositório, torne-o privado e adicione os usuários **@cgromulo** e **@abreufilho** como colaboradores usando o link abaixo:
  * >https://github.com/SEU_USUARIO/frontend-test-jul-2024/settings/access
* Faça as alterações de modo a cumprir as tarefas deste teste:
    * Realize um commit por feature
    * O resultado final deve estar dentro de um pull request (merge completo) no seu próprio repositório (lembrando de fazê-lo antes do prazo final mencionado no email que você recebeu).
* Lembre-se de utilizar sua conta real do GitHub;
* O tempo de entrega *NÃO* está sendo avaliado, mas envios após a data e hora limite serão desconsiderados.
* Nenhum código desenvolvido neste teste será utilizado em produção/comercialmente pela TerraQ.
* Ao concluir o seu PULL REQUEST, envie um e-mail para contato@terraq.com.br contendo somente o link para seu repositório no corpo do texto e o título do e-mail contendo *"Teste frontend [Seu Nome]"*, ex.:
  >De: **seunome@gmail.com**

  >Para: **contato@terraq.com.br**

  >Título: **Teste frontend [Seu Nome]**

  >Corpo do e-mail: **https://github.com/{usuario}/frontend-test-jul-2024**
   
# Instruções de instalação/configuração

Utilize o link a seguir para gerar uma cópia local do repositório:
> https://github.com/terra-q/frontend-test-jul-2024/generate

Após a cópia, clone o repositório localmente:

```
git clone https://github.com/<SEU_USUARIO>/frontend-test-jul-2024.git
```

Instale as dependências do projeto:

```
composer install
npm install
```

Depois copie o arquivo `.env.example` para `.env`:

```
cp .env.example .env
```

Crie um banco de dados temporário para a aplicação com o comando abaixo (ou crie-o manualmente, se preferir):
    
```
sudo -u postgres psql -c "CREATE DATABASE terraq_teste"
```

Depois, gere a chave da aplicação:

```
php artisan key:generate
```

Rode a migração para criar as tabelas no banco de dados:

```
php artisan migrate
```

E por fim, inicie o servidor local da Aplicação:

```
php artisan serve
```

E o servidor de desenvolvimento do Vue em outro terminal:

```
npm run dev
```

Acesse a aplicação em http://localhost:8000.

(Este repositório utiliza Laravel 9)
