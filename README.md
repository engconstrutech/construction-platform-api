# construction-platform-api

Projeto de api para a plataforma de construção civil

## Padrão com gitflow

Usar o seguinte link para entendimento do padrão e suas vertentes:

[**Git Flow: entenda o que é, como e quando utilizar**](https://www.alura.com.br/artigos/git-flow-o-que-e-como-quando-utilizar?utm_term=&utm_campaign=topo-aon-search-gg-dsa-artigos_conteudos&utm_source=google&utm_medium=cpc&campaign_id=11384329873_164240702375_703853654617&utm_id=11384329873_164240702375_703853654617&hsa_acc=7964138385&hsa_cam=topo-aon-search-gg-dsa-artigos_conteudos&hsa_grp=164240702375&hsa_ad=703853654617&hsa_src=g&hsa_tgt=aud-527303763294:dsa-2276348409543&hsa_kw=&hsa_mt=&hsa_net=google&hsa_ver=3&gad_source=1&gad_campaignid=11384329873&gbraid=0AAAAADpqZIAsvrOkQkVitDVDy0JMWKDIF&gclid=Cj0KCQjwmK_CBhCEARIsAMKwcD6gh4gPogo49cSFRDGpHwJ0gYqqaalfM81rAWsPtd5bDBIc_0EFNYcaAs-bEALw_wcB#o-que-e-git-flow)

### Iniciar um novo branch (exemplo a partir da develop)

git flow feature start [nome-da-feature]

git flow bugfix start [nome-do-bugfix]

git flow release start [nome-da-release]

### Finalizar um branch

git flow feature finish [nome-da-feature]

## Como rodar o projeto

docker-compose up --build

## Acessar o container

**docker-compose exec -it app sh** (padrão do linux alpine)

ou

**docker-compose exec -it app bash** (caso tenha o bash instalado no container)

## Instalar alguma biblioteca

Com o container rodando:

docker-compose exec app go get -u [biblioteca]

Exemplo: **docker-compose exec app go get -u github.com/gin-gonic/gin**

## Parar o container

Parar e remover o container: **docker-compose down -v**

Limpar recursos Docker não usados: **docker system prune -f**

## Criar arquivos de migração

migrate create -ext sql -dir internal/infrastructure/db/postgres/migrations nome-da-migracao

Exemplo: migrate create -ext sql -dir internal/infrastructure/db/postgres/migrations create_test_table