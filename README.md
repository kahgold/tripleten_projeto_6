# Projeto: Zuber

Neste projeto, analisei a Zuber, uma nova empresa de compartilhamento de caronas que está sendo lançada em Chicago. Minha tarefa é encontrar padrões nas informações disponíveis. Entender as preferências dos passageiros e o impacto de fatores externos sobre as caronas. Trabalhando com um banco de dados, analisei dados de concorrentes e testei uma hipótese sobre o impacto do clima na frequência das viagens.

*A parte do SQL foi feita na plataforma tripleten, mas as tarefas e os códigos estão na parte do código SQL nos arquivos*

**Descrição dos dados (SQL)**

Um banco de dados com informações sobre viagens de táxi em Chicago:
Tabela de bairros: dados sobre os bairros da cidade
- `nome`: nome do bairro
- `neighborhood_id`: código do bairro

Tabela cabs: dados sobre os táxis
- `cab_id`: código do veículo
- `vehicle_id`: a identificação técnica do veículo
- `company_name`: a empresa proprietária do veículo

Tabela trips: dados sobre viagens
- `trip_id`: código da viagem
- `cab_id`: código do veículo que está operando a corrida
- `start_ts`: data e hora do início da corrida (hora arredondada para a hora)
- `end_ts`: data e hora do final da corrida (hora arredondada para a hora)
- `duration_seconds`: duração da corrida em segundos
- `distance_miles`: distância percorrida em milhas
- `pickup_location_id`: código do bairro de coleta
- `dropoff_location_id`: código do bairro de entrega

Tabela weather_records: dados meteorológicos
- `record_id`: código do registro meteorológico
- `ts`: data e hora dos registros (hora arredondada para a hora)
- `temperatura`: temperatura quando o registro foi feito
- `description`: breve descrição das condições meteorológicas, por exemplo, "chuva leve" ou "nuvens esparsas".

**Python**

Agora você tem esses dois CSVs: 
- project_sql_result_01.csv. Contém os seguintes dados:
  - `company_name`: nome da empresa de táxi
  - `trips_amount`: o número de corridas para cada empresa de táxi de 15 a 16 de novembro de 2017.

- project_sql_result_04.csv. Contém os seguintes dados:
  - `dropoff_location_name`: bairros de Chicago onde as corridas terminaram
  - `average_trips`: o número médio de viagens que terminaram em cada bairro em novembro de 2017.

- project_sql_result_07.csv. Contém os seguintes daddos:
  - `start_ts`: data e hora de coleta
  - `weather_conditions`: condições meteorológicas no momento em que a corrida começou
  - `duration_seconds`: duração da corrida em segundos

Teste a hipótese: "A duração média das viagens do Loop para o Aeroporto Internacional O'Hare muda em sábados chuvosos."

**Conclusão** 

*Nossa jornada de análise de dados nos levou a descobrir insights valiosos sobre as preferências dos passageiros e o impacto do clima nas corridas de táxi. À medida que exploramos os dados, desvendamos padrões que nos permitirão aprimorar nossos serviços e tornar as viagens mais agradáveis para nossos passageiros. Nossa análise revelou que a `Flash Cab` é uma empresa consolidada com uma alta demanda por viagens, sugerindo que eles possuem uma frota considerável. Além disso, companhias afiliadas e associadas também desempenham um papel importante no setor.*

*Identificamos os destinos mais requisitados, com áreas centrais da cidade, como `River North`, `Streeterville`, `West Loop` e `Loop`, consistentemente no Top 10. Esses insights nos orientam a melhor posicionar nossa frota no distrito de negócios de Chicago, onde a demanda é mais alta. Nossa análise também revelou que algumas corridas com tempo de duração igual a zero foram canceladas ou tiveram problemas na extração de dados, e também tomamos medidas para tratar os devidos outliers nos dados.*

*Geramos diversos gráficos para ilustrar nossas análises, dividimos as companhias em grupos e identificamos que, se quisermos atingir a liderança no setor, devemos nos inspirar nas empresas que se encontram no primeiro quartil (Q1) das métricas de desempenho. Além disso, constatamos que é relevante estabelecer associações e afiliações, considerando a média de viagens. Nossos estudos mostram que as condições climáticas impactam diretamente o comportamento dos usuários, afetando os horários, a frequência de uso e a duração das viagens.*

*Concluímos que em dias ruins, as viagens tendem a ser mais longas, enquanto em dias bons, os clientes utilizam mais os táxis. Nossos gráficos de dispersão destacaram demandas de horários específicos, com picos notáveis durante o horário de almoço e início da manhã, dependendo das condições climáticas.*

*Verificamos que a hora do dia tem uma influência significativa na duração da viagem, conforme evidenciado pela matriz de correlação que geramos. Além disso, testamos a hipótese de que a duração média das viagens do Loop para o Aeroporto Internacional O'Hare muda nos sábados chuvosos em comparação com os sábados não chuvosos. Nossos testes utilizando o método t-Student rejeitaram a hipótese nula, confirmando que a duração média das viagens realmente varia nos sábados chuvosos. Para reforçar nossos resultados, aplicamos o método bootstrap e obtivemos os mesmos resultados, validando assim nossa análise.*
