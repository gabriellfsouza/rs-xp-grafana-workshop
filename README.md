# wevo-rocketseat-microservice-jwt

Palestra para o Rocketseat : Monitoramento de Regra de negocio com Grafana + Nodejs

## Gerando métricas de negócio com Nodejs e Grafana

Dashboards em tempo real

Pablo Almeida

- Lider de produtos / arquiteto
  Fenando Vieira
- Lider técnico de produtos

Wevo -> integração como serviço

RabbitMQ (80 milhões de requests)
Flow -> 75 milhões de integrações por dia
+1800 usuários

Cenário -> Monitorar com uma dashboar a quantidade de pedidos vendidos

Monitoramento do tipo: Push

Monitoramento do tipo: Pull (coletar a partir da hora que o deshboard é exibido)

### Grafana

Visualização de dados de uma forma amigável

- monitora infra
- aplicativos
- usina de energia
- colmeia

possível configurar alertas
dark theme

Grafana só exibe os dados

#### Dashboards

O grafana já possui dashboards pré feitos, plugins (componentes de dashboard)

## Prometheus Server

Banco de dados temporal

Pode se conectar ao mongo, elastics, redis
DataBase temporal (usa regra de negócios)
coleta métricas de infraestrutura por exemplo ou até mesmo regras de negócio

Banco de dados temporal

- é possível configurar alertas também (possui cruzamento de métricas para alertas)
- mantido na cloud native computing foundation
- camada target, onde são configurados os endpoints dos exporters
  PromQL - Linguagem própria para consulta

Counter
Gauge
Hisotogram
Summary

https://prometheus.io/docs/concepts/metric_types/

#### Exporters

- reponsáveis por obter métricas desejadas e expor via https
- já existem vários exporters prontos
- por padrão os exporters expõem na rota /metrics

#### Como construir um exporter com nodejs?

- Utilizar a biblioteca prom-client do prometheus
- Métics devem ter um prefixo
  _monitoramento*pedidos*\${metrica}_
  _monitoramento_pedidos_total_pedidos_
- A métrica tem que fazer sentido (somada ou na média)

#### Arquitetura de monitoramento

Grafana
Prometheus
Aplicação
Database

- esta é uma arquitetura neartime

git clone https://github.com/pabloalmeidas13/rocketseat-metrics-grafana-nodejs

cd src/app-pedidos
npm install
npm start

vagas@wevo.com.br
www.wevo.com.br

#wevolution (podcast wevo)
Metabase
