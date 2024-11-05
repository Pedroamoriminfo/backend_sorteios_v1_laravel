
# API de Estatísticas e Previsão de Jogos de Loteria

Este projeto é uma API desenvolvida em **Laravel** que consome dados da loteria para gerar estatísticas e prever combinações de números com maior probabilidade de ocorrência. A API oferece informações sobre resultados passados, previsões e cálculo de probabilidades, ajudando usuários a criar jogos de forma mais estratégica.

## Funcionalidades

- **Histórico de Resultados**: Consulta e exibe resultados passados para análise.
- **Previsão de Números**: Algoritmos estatísticos para sugerir combinações com alta chance de ocorrência.
- **Cálculo de Probabilidade**: Retorna a probabilidade de uma combinação de números escolhida vencer.
- **Sugestões de Jogos**: Com base em padrões estatísticos, sugere números promissores.

## Tecnologias Utilizadas

- **Laravel**: Framework PHP para desenvolvimento backend.
- **MySQL**: Banco de dados para armazenamento de informações históricas de jogos.
- **Algoritmos Estatísticos**: Para cálculos de previsão e probabilidades.

## Configuração e Instalação

1. **Clone o repositório**:
   ```bash
   git clone https://github.com/Pedroamoriminfo/backend_sorteios_v1_laravel.git
   ```
   
2. **Instale as dependências**:
   ```bash
   composer install
   ```

3. **Configuração do Ambiente**:
   - Duplique o arquivo `.env.example` e renomeie para `.env`.
   - Configure as variáveis de ambiente, incluindo detalhes do banco de dados.

4. **Gere a chave da aplicação**:
   ```bash
   php artisan key:generate
   ```

5. **Execute as migrações e seeders para o banco de dados**:
   ```bash
   php artisan migrate --seed
   ```

6. **Inicie o servidor local**:
   ```bash
   php artisan serve
   ```

A API estará disponível em `http://localhost:8000`.

## Endpoints

### 1. Histórico de Resultados

- **Rota**: `/api/historico`
- **Método**: GET
- **Descrição**: Retorna o histórico de resultados de jogos de loteria.
- **Resposta Exemplo**:
    ```json
    {
      "data": [
        {"data": "2024-11-01", "numeros": [3, 12, 24, 32, 40, 55]}
      ]
    }
    ```

### 2. Previsão de Números

- **Rota**: `/api/previsao`
- **Método**: GET
- **Descrição**: Retorna números com maior probabilidade de serem sorteados.
- **Resposta Exemplo**:
    ```json
    {
      "previsao": [3, 15, 27, 36, 44, 58]
    }
    ```

### 3. Probabilidade de Jogo

- **Rota**: `/api/probabilidade`
- **Método**: POST
- **Descrição**: Calcula a probabilidade de um conjunto de números vencer.
- **Parâmetros**:
    - `numeros` (array): Lista de números para o cálculo.
- **Corpo Exemplo**:
    ```json
    {
      "numeros": [3, 15, 27, 36, 44, 58]
    }
    ```
- **Resposta Exemplo**:
    ```json
    {
      "probabilidade": "0.0004%"
    }
    ```

## Exemplos de Uso

### Obter histórico de resultados
```bash
curl -X GET http://localhost:8000/api/historico
```

### Obter previsão de números
```bash
curl -X GET http://localhost:8000/api/previsao
```

### Calcular probabilidade de um jogo
```bash
curl -X POST http://localhost:8000/api/probabilidade -H "Content-Type: application/json" -d '{"numeros": [3, 15, 27, 36, 44, 58]}'
```

## Testes

Para executar os testes automatizados:

```bash
php artisan test
```

## Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo `LICENSE` para mais detalhes.

---

**Desenvolvido por Pedro Amorim**
