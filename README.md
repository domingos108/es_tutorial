# Elastic Search Tutorial
-  Download
Link para baixar os arquivos: https://www.elastic.co/pt/start


##### Conceitos iniciais:
- Documents: Json que corresponde a unidade de armazenamento base;
- Fields: Campo em um documento;
- Index: Partição composta por documentos;

 <pre>
{
   "_id": 3,
   "_index": ["your index name"],
   "_source":{
       "age": 28,
       "name": ["daniel”],
       "year":1989,
    }
}
</pre>
##### Criando e populando um index
- Iniciar serviços:
    - bin/elasticsearch
    - bin/kibana
    - http://localhost:5601
- Criação do index:
    - PUT /es_tutorial
- Ingestão:
 <pre>
PUT /es_tutorial/_doc/1
{
  "texto": "Isso é uma movimentação de um processo que representa um despacho",
  "numero_processo": "0003123220155060002",
  "partes": [
    {
      "nome": "INSTITUTO NACIONAL DO SEGURO SOCIAL INSS",
      "papel": "REU"
    },
    {
      "nome": "JURACY ANTONIO DE JESUS",
      "papel": "AUTOR"
    },
    {
      "nome": "NASCIMENTO JOÃO BORGES",
      "papel": "ADVOGADO"
    }
  ]
}
POST /es_tutorial/_doc/_bulk
{"index":{"_id":"2"}}
{"texto":"DATA ATRIBUIÇÃO 10/10/2007 - Turma 05.","numero_processo":"0003123220155060002","partes":[{"nome":"TANJIRO KAMADO","papel":"REU"},{"nome":"UZUMAKI NARUTO","papel":"AUTOR"},{"nome":"MIDORIYA IZUKU","papel":"ADVOGADO"},{"nome":"MONKEY D LUFFY","papel":"ADVOGADO"}]}
{"index":{"_id":"3"}}
{"texto":"Notificação: Quanto ao despacho proferido: Acordo homologado em 12.03.2010. A reclamada deverá discriminar em 10 dias as parcelas de natureza salarial e as de natureza indenizatória,sob pe- na de ser considerada a totalidade de natureza salarial. ","numero_processo":"0000151220185060203","partes":[{"nome":"BOM PREÇO MERCADINHO","papel":"REU"},{"nome":"DOMINGOS SEGUNDAS TERÇAS","papel":"AUTOR"},{"nome":"DIAS DA SEMANA","papel":"ADVOGADO"}]}
{"index":{"_id":"4"}}
{"texto":"Ciência da conversão da tramitação do processo do meio físico para o eletrônico. No prazo de 30 (trinta) dias, adotar as providências à regular tramitação do feito no meio eletrônico, inclusive o prévio credenciamento no sistema, nos moldes dos arts. 5o e 8o da Resolução CSJT no 136/2014. A vista e a extração de cópias dos processos cuja tramitação foi convertida para o Processo Judicial Eletrônico-PJe- JT poderá ser realizada na Coordenadoria de Gestão Documental eMemória depois de transcorridos 10 (dez) dias da juntada das peças digitalizadas ao PJe.","numero_processo":"0012340320125060001","partes":[{"nome":"Instituto de Assistencia Medica Ao Servidor Public","papel":"REU"},{"nome":"ANDRE DA SILVA","papel":"AUTOR"},{"nome":"ADVOGADO PALOMA","papel":"ADVOGADO"}]}
{"index":{"_id":"5"}}
{"texto":"JULGAMENTO PARA 13/11/2007 às 13:00 Hs. - 10a TURMA . No de ordem: 258 . ","numero_processo":"0003123040095060032","partes":[{"nome":"RILMA APARECIDA HEMETÉRIO","papel":"REU"},{"nome":"MARTA CASADEI MOMEZZO","papel":"AUTOR"},{"nome":" MOMEZZO CASADEI","papel":"ADVOGADO"}]}
</pre>
- Atualização

- Exclusão
<pre>
DELETE /es_tutorial/_doc/1
</pre>
#### Componentes do index
![es_arq](https://codingexplained.com/wp-content/uploads/4-1024x835.png)
 Imagem disponível em: https://codingexplained.com/coding/elasticsearch/understanding-replication-in-elasticsearch
 - mappings
 - shards
 - nodes
 - replicas
 
#### Busca de documentos
- Busca

