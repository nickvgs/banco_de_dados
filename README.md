erDiagram
    CLIENTES ||--o{ VEICULOS : "possui"
    VEICULOS ||--o{ ORDENS_SERVICO : "gera"
    MECANICOS ||--o{ ORDENS_SERVICO : "executa"
    ORDENS_SERVICO ||--|{ ITENS_SERVICO : "contém"
    SERVICOS ||--|{ ITENS_SERVICO : "é incluído"

    CLIENTES {
        int id_cliente PK
        string nome
        string cidade
    }

    VEICULOS {
        int id_veiculo PK
        string modelo
        int ano
        int id_cliente FK
    }

    MECANICOS {
        int id_mecanico PK
        string nome
        string especialidade
    }

    ORDENS_SERVICO {
        int id_os PK
        date data_emissao
        decimal valor_total
        string status
        int id_veiculo FK
        int id_mecanico FK
    }

    SERVICOS {
        int id_servico PK
        string descricao
        decimal preco_base
    }

    ITENS_SERVICO {
        int id_os PK, FK
        int id_servico PK, FK
        int quantidade
    }
