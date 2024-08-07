# Tabelas de Gestão de Frotas
## Veiculo

| Parâmetro                | Tipo de Dado | Descrição                                                        |
|--------------------------|--------------|------------------------------------------------------------------|
| id                       | integer      | Identificador único do veículo                                   |
| placa                  | string       | Placa do veículo                                                 |
| chassi                 | string       | Número do chassi do veículo                                      |
| modelo                 | string       | Modelo do veículo                                                |
| renavam                | string       | Número do RENAVAM do veículo                                     |
| ano_fabricacao         | integer      | Ano de fabricação do veículo                                     |
| ano_modelo             | integer      | Ano do modelo do veículo                                         |
| tipo_combustivel       | string       | Tipo de combustível (e.g., gasolina, álcool, diesel, elétrico)   |
| tanque                 | integer      | Tamanho do tanque de combustível do veículo                      |
| numero_portas          | integer      | Número de portas do veículo                                      |
| tipo_de_cambio_id       | string       | Tipo de câmbio (manual, automático, CVT)                         |
| fabricante_veiculo_id  | integer      | Identificador do fabricante do veículo                           |
| cor_veiculo_id         | integer      | Identificador da cor do veículo                                 |
| created_at             | datetime     | Timestamp de criação (gerado automaticamente pelo Rails) |
| updated_at             | datetime     | Timestamp de atualização (gerado automaticamente pelo Rails) |


## Tipo_Cambio

| Parâmetro            | Tipo de Dado | Descrição                                             |
|----------------------|--------------|-------------------------------------------------------|
| id                   | integer      | Identificador único do tipo de câmbio                 |
| nome               | string       | Nome do tipo de câmbio (e.g., Manual, Automático, CVT)|
| descricao          | text         | Descrição adicional sobre o tipo de câmbio            |
| created_at             | datetime     | Timestamp de criação (gerado automaticamente pelo Rails) |
| updated_at             | datetime     | Timestamp de atualização (gerado automaticamente pelo Rails) |


## Cor_Veiculo

| Parâmetro              | Tipo de Dado | Descrição                                   |
|------------------------|--------------|---------------------------------------------|
| id                     | integer      | Identificador único da cor do veículo       |
| nome                 | text         | Nome da cor do veículo                      |
| created_at             | datetime     | Timestamp de criação (gerado automaticamente pelo Rails) |
| updated_at             | datetime     | Timestamp de atualização (gerado automaticamente pelo Rails) |


## Tipo_Veiculo

| Parâmetro              | Tipo de Dado | Descrição                                      |
|------------------------|--------------|------------------------------------------------|
| id                     | integer      | Identificador único do tipo de veículo         |
| nome                 | string       | Nome do tipo de veículo                        |
| descricao            | text         | Descrição do tipo de veículo(barco, empilhadeira)                |
| created_at             | datetime     | Timestamp de criação (gerado automaticamente pelo Rails) |
| updated_at             | datetime     | Timestamp de atualização (gerado automaticamente pelo Rails) |


## Fabricante_Veiculo

| Parâmetro              | Tipo de Dado | Descrição                                      |
|------------------------|--------------|------------------------------------------------|
| id                     | integer      | Identificador único do fabricante do veículo   |
| nome                 | string       | Nome do fabricante do veículo                  |
| descricao            | text         | Descrição do fabricante do veículo             |
| created_at             | datetime     | Timestamp de criação (gerado automaticamente pelo Rails) |
| updated_at             | datetime     | Timestamp de atualização (gerado automaticamente pelo Rails) |


## Frota

| Parâmetro                | Tipo de Dado | Descrição                                                |
|--------------------------|--------------|----------------------------------------------------------|
| id                       | integer      | Identificador único da frota                             |
| nome                   | string       | Nome da frota                                            |
| descricao              | text         | Descrição da frota (responsável e etc.)                 |
| disponibilidade_agendamento | boolean  | Disponibilidade para agendamento de frota                 |
| data_aquisicao         | date         | Data de aquisição da frota                              |
| valor_aquisicao        | decimal      | Valor da aquisição da frota                             |
| status                 | string       | Status da frota (disponível, vendido, em manutenção)     |
| capacidade_passageiros | integer      | Capacidade de passageiros                                |
| observacoes            | text         | Observações adicionais sobre a frota                    |
| localidade_id          | string       | Localidade da frota                                     |
| tipo_veiculo_id        | integer      | Identificador do tipo de veículo (carro, moto, caminhão, barco) |
| veiculo_id             | integer      | Relacionamento com o veículo                             |
| created_at             | datetime     | Timestamp de criação (gerado automaticamente pelo Rails) |
| updated_at             | datetime     | Timestamp de atualização (gerado automaticamente pelo Rails) |


## condutor

| Parâmetro                 | Tipo de Dado | Descrição                                                   |
|---------------------------|--------------|-------------------------------------------------------------|
| id                        | integer      | Identificador único do condutor                            |
| user_id                | integer      | Identificador do usuário (referência à tabela `user`)   |
| numero_habilitacao        | string       | Número da habilitação para dirigir                          |
| validade_habilitacao      | date         | Data de validade da habilitação                             |
| tipo_responsabilidade     | string       | Tipo de responsabilidade (e.g., Condutor principal, substituto) |
| categoria_habilitacao_id     | string       | Identificador do Categoria da habilitacao (referência à Categoria_habilitação (e.g., A, B, C, D) |
| created_at             | datetime     | Timestamp de criação (gerado automaticamente pelo Rails) |
| updated_at             | datetime     | Timestamp de atualização (gerado automaticamente pelo Rails) |

## categoria_habilitacao
| id                     | integer      | Identificador único |
| nome                | string       | Sigla da categria habilitação                  |
| descricao            | text         | Descrição da categoria             |
| created_at             | datetime     | Timestamp de criação (gerado automaticamente pelo Rails) |
| updated_at             | datetime     | Timestamp de atualização (gerado automaticamente pelo Rails) |






## Centro de Custo

| Parâmetro           | Tipo de Dado | Descrição                                               |
|---------------------|--------------|---------------------------------------------------------|
| id                  | integer      | Identificador único do centro de custo                  |
| nome              | string       | Nome do centro de custo                                 |
| descricao         | text         | Descrição do centro de custo                            |
| codigo            | string       | Código do centro de custo                               |
| departamento_id   | integer      | Identificador do departamento associado                 |
| gerente_id        | integer      | Identificador do gerente responsável                    |
| orcamento         | decimal      | Orçamento alocado para o centro de custo                |
| data_criacao      | date         | Data de criação do centro de custo                      |
| ativo             | boolean      | Status indicando se o centro de custo está ativo        |
| data_inativacao   | date         | Data de inativação do centro de custo, se aplicável     |
| created_at             | datetime     | Timestamp de criação (gerado automaticamente pelo Rails) |
| updated_at             | datetime     | Timestamp de atualização (gerado automaticamente pelo Rails) |

