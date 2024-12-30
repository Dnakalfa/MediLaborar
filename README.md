# API de Gerenciamento de Clínica Médica

## Descrição
Esta API foi desenvolvida para gerenciar informações de uma clínica médica, permitindo o cadastro, consulta, atualização e remoção de médicos e suas especialidades em um banco de dados.

## Funcionalidades
- **Cadastro de Médicos:** Permite criar registros de médicos com dados gerais e especialidades.
- **Consulta de Médicos:** Recupera informações de médicos, com suporte a filtros como nome, especialidade e ID.
- **Atualização de Dados:** Atualiza informações cadastrais de médicos.
- **Remoção de Médicos:** Exclui registros de médicos do banco de dados.

## Tecnologias Utilizadas
- **Linguagem:** Java
- **Framework:** Spring Boot
- **Banco de Dados:** MySQL
- **Documentação:** Swagger

## Endpoints

### 1. Cadastro de Médicos
**Descrição:** Adiciona um novo médico ao sistema.

- **URL:** `/api/medicos`
- **Método:** `POST`
- **Corpo da Requisição:**
```json
{
  "nome": "Dr. João Silva",
  "crm": "123456",
  "especialidades": ["Cardiologia", "Clínica Geral"]
}
```
- **Resposta Sucesso:**
```json
{
  "id": 1,
  "nome": "Dr. João Silva",
  "crm": "123456",
  "especialidades": ["Cardiologia", "Clínica Geral"]
}
```

### 2. Consulta de Médicos
**Descrição:** Recupera a lista de médicos cadastrados ou detalhes de um médico específico.

- **URL:** `/api/medicos`
- **Método:** `GET`
- **Parâmetros de Consulta:**
  - `nome` (opcional): Filtra médicos pelo nome.
  - `especialidade` (opcional): Filtra médicos por especialidade.
  - `id` (opcional): Retorna dados de um médico específico.

**Resposta Sucesso:**
```json
[
  {
    "id": 1,
    "nome": "Dr. João Silva",
    "crm": "123456",
    "especialidades": ["Cardiologia", "Clínica Geral"]
  }
]
```

### 3. Atualização de Dados de Médico
**Descrição:** Atualiza informações cadastrais de um médico existente.

- **URL:** `/api/medicos/{id}`
- **Método:** `PUT`
- **Corpo da Requisição:**
```json
{
  "nome": "Dr. João Pedro Silva",
  "crm": "654321",
  "especialidades": ["Neurologia"]
}
```
- **Resposta Sucesso:**
```json
{
  "id": 1,
  "nome": "Dr. João Pedro Silva",
  "crm": "654321",
  "especialidades": ["Neurologia"]
}
```

### 4. Remoção de Médico
**Descrição:** Remove um médico do sistema.

- **URL:** `/api/medicos/{id}`
- **Método:** `DELETE`
- **Resposta Sucesso:**
```json
{
  "message": "Médico removido com sucesso."
}
```

## Instalação e Execução

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/clinica-api.git
   ```

2. Configure o banco de dados MySQL no arquivo `application.properties`:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/clinica
   spring.datasource.username=seu-usuario
   spring.datasource.password=sua-senha
   spring.jpa.hibernate.ddl-auto=update
   ````

3. Compile e execute a aplicação:
   ```bash
   mvn spring-boot:run
   ```

4. Acesse a documentação da API no navegador:
   - URL: `http://localhost:8080/swagger-ui/index.html`

## Contribuição
Contribuições são bem-vindas! Sinta-se à vontade para abrir um **pull request** ou relatar **issues** no repositório.

## Licença
Este projeto é licenciado sob a **MIT License**. Consulte o arquivo `LICENSE` para mais detalhes.
