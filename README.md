# Senheiro-Norris

EADME do programa - Senheiro Norris:

- .NET 9
- Visual Studio 2022
- Postman, APIDOG ...

- Valide a porta onde a aplicação esta rodando de fato.
- Use Postman ou APIDOG para realizar as requisições.
- Logs são gerados na pasta Documentos do User.


Utilizando o APP

1.	Executar o Programa:
•	O app estará rodando no host padrão, exemplo: https://localhost:5001 
(check no CMD de execução a porta sendo executada e ALTERE ANTES de executar as requisições).

2.	Emissão de Senha:
•	Executando: POST https://localhost:7279/senha/emitir
•	Será gerado um JSON:

{
    "id": 5,
    "codigo": "3a55becd-1dff-41ae-9ad3-7afd416ba688",
    "dataEmissao": "2025-02-23T22:03:34.9542382-03:00",
    "dataFinalizacao": null,
    "dataCanceladaManual": null,
    "status": "Ativa",
    "informacaoExtra": "Every time Chuck Norris watches on Olympic event, he wins a gold medal."
}

3.	Finalizando Senha:

•	Para finalizar uma senha específica, passando o ID da senha na URL.
•	Executando: POST https://localhost:7279/senha/finalizar/{id}
•	Será gerado um JSON:

{
    "id": 1,
    "codigo": "636bf43a-8e57-46dd-bc45-6c67b07de0a6",
    "dataEmissao": "2025-02-23T22:03:19.0914026-03:00",
    "dataFinalizacao": "2025-02-23T22:06:28.0339745-03:00",
    "dataCanceladaManual": null,
    "status": "Finalizada",
    "informacaoExtra": "Chuck Norris considers Ben Hur to be a midget."
}

4.	Cancelando Senha - MANUAL:

•	Para cancelar uma senha específica, passando o ID da senha na URL.
•	Executando: POST https://localhost:7279/senha/cancelar/{id}
•	Será gerado um JSON:

{
    "id": 2,
    "codigo": "b19babc9-4b3b-45b6-bbb2-825a4f8adb05",
    "dataEmissao": "2025-02-23T22:03:22.433095-03:00",
    "dataFinalizacao": null,
    "dataCanceladaManual": "2025-02-23T22:07:14.508181-03:00",
    "status": "Cancelada manualmente",
    "informacaoExtra": "Chuck Norris does not live in a yellow submarine."
}


5.	Cancelando Senha - automatico:
•	 A CADA 5 MINUTOS O SISTEMA CANCELA AS SENHAS ATIVAS :)

6.	Consulta de Senhas:
•	GET para listar TODAS as senhas.
•	Executando: GET https://localhost:7279/senha/listar
•	Será gerado um JSON:

[
    {
        "id": 1,
        "codigo": "636bf43a-8e57-46dd-bc45-6c67b07de0a6",
        "dataEmissao": "2025-02-23T22:03:19.0914026-03:00",
        "dataFinalizacao": "2025-02-23T22:06:28.0339745-03:00",
        "dataCanceladaManual": null,
        "status": "Finalizada",
        "informacaoExtra": "Chuck Norris considers Ben Hur to be a midget."
    },
    {
        "id": 2,
        "codigo": "b19babc9-4b3b-45b6-bbb2-825a4f8adb05",
        "dataEmissao": "2025-02-23T22:03:22.433095-03:00",
        "dataFinalizacao": null,
        "dataCanceladaManual": "2025-02-23T22:07:14.508181-03:00",
        "status": "Cancelada manualmente",
        "informacaoExtra": "Chuck Norris does not live in a yellow submarine."
    },
    {
        "id": 3,
        "codigo": "74f08195-1c8a-469b-b2cb-3008a4417ffb",
        "dataEmissao": "2025-02-23T22:03:25.976526-03:00",
        "dataFinalizacao": null,
        "dataCanceladaManual": "2025-02-23T22:08:39.9961387-03:00",
        "status": "Cancelada manualmente",
        "informacaoExtra": "Chuck Norris' Christmas tree is actually a 20 foot Tesla coil. It is also necessary to power his electric beard trimmer."},
    {
       "id": 4,
        "codigo": "48897308-cfc2-49e9-96c4-7ac85b4ebdc2",
        "dataEmissao": "2025-02-23T22:03:31.3936689-03:00",
        "dataFinalizacao": null,
        "dataCanceladaManual": "2025-02-23T22:08:53.3475329-03:00",
        "status": "Cancelada",
        "informacaoExtra": "Faster than a speeding bullet ... more powerful than a locomotive ... able to leap tall buildings in a single bound... yes, these are some of Chuck Norris's warm-up exercises."},
    {
        "id": 5,
        "codigo": "3a55becd-1dff-41ae-9ad3-7afd416ba688",
        "dataEmissao": "2025-02-23T22:03:34.9542382-03:00",
        "dataFinalizacao": null,
        "dataCanceladaManual": null,
        "status": "Ativa",
        "informacaoExtra": "Every time Chuck Norris watches on Olympic event, he wins a gold medal."
    }
]
