### Documento Markdown para Monitoramento de Níveis de Toner da Impressora EPSON WF-C878R

```markdown
# Monitoramento de Níveis de Toner da Impressora EPSON WF-C878R no Zabbix

## OIDs para Níveis de Toner

- **Nível de toner preto**:
  ```plaintext
  iso.3.6.1.2.1.43.11.1.1.9.1.1
  ```

- **Nível de toner ciano**:
  ```plaintext
  iso.3.6.1.2.1.43.11.1.1.9.1.2
  ```

- **Nível de toner magenta**:
  ```plaintext
  iso.3.6.1.2.1.43.11.1.1.9.1.3
  ```

- **Nível de toner amarelo**:
  ```plaintext
  iso.3.6.1.2.1.43.11.1.1.9.1.4
  ```

## Criar Template no Zabbix

1. **Criar um Novo Template**:
   - Vá para **Configuração** > **Templates**.
   - Clique em **Criar template**.
   - Preencha os campos necessários, como o nome do template (por exemplo, "EPSON WF-C878R Toner Levels").

2. **Adicionar Itens ao Template**:
   - No template recém-criado, vá para a aba **Itens** e clique em **Criar item**.
   - Adicione os itens para cada nível de toner usando os OIDs que você obteve:

     - **Nível de toner preto**:
       ```plaintext
       Nome: Nível de Toner Preto
       Tipo: SNMPv2 agent
       Chave: toner.black
       OID: iso.3.6.1.2.1.43.11.1.1.9.1.1
       Tipo de Informação: Numérico (inteiro)
       Unidades: %
       ```

     - **Nível de toner ciano**:
       ```plaintext
       Nome: Nível de Toner Ciano
       Tipo: SNMPv2 agent
       Chave: toner.cyan
       OID: iso.3.6.1.2.1.43.11.1.1.9.1.2
       Tipo de Informação: Numérico (inteiro)
       Unidades: %
       ```

     - **Nível de toner magenta**:
       ```plaintext
       Nome: Nível de Toner Magenta
       Tipo: SNMPv2 agent
       Chave: toner.magenta
       OID: iso.3.6.1.2.1.43.11.1.1.9.1.3
       Tipo de Informação: Numérico (inteiro)
       Unidades: %
       ```

     - **Nível de toner amarelo**:
       ```plaintext
       Nome: Nível de Toner Amarelo
       Tipo: SNMPv2 agent
       Chave: toner.yellow
       OID: iso.3.6.1.2.1.43.11.1.1.9.1.4
       Tipo de Informação: Numérico (inteiro)
       Unidades: %
       ```

3. **Adicionar Triggers (Opcional)**:
   - Você pode adicionar triggers para alertar quando os níveis de toner estiverem baixos. Vá para a aba **Triggers** no template e clique em **Criar trigger**.
   - Exemplo de trigger para toner preto:
     ```plaintext
     Nome: Toner Preto Baixo
     Expressão: {EPSON WF-C878R Toner Levels:toner.black.last()}<20
     Gravidade: Aviso
     ```

4. **Associar o Template ao Host**:
   - Vá para **Configuração** > **Hosts**.
   - Selecione o host da impressora EPSON WF-C878R e vá para a aba **Templates**.
   - Clique em **Selecionar** e adicione o template que você criou.

5. **Verificar os Dados**:
   - Após associar o template, o Zabbix começará a coletar dados dos níveis de toner. Você pode verificar os dados em **Monitoramento** > **Últimos dados**.

## Recursos Adicionais

Para mais detalhes sobre a criação de templates e itens no Zabbix, você pode consultar a documentação oficial do Zabbix.

```

Você pode copiar e colar este conteúdo em um arquivo Markdown (`README.md`, por exemplo) e adicioná-lo ao seu repositório no GitHub. Se precisar de mais alguma coisa, estou aqui para ajudar!
