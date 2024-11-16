!see info.png


Para obter os OIDs exatos para a sua impressora EPSON WorkForce Pro WF-C878R, recomendo usar uma ferramenta de gerenciamento SNMP, como snmpwalk, para explorar a MIB da impressora e identificar os OIDs disponíveis. Aqui está um exemplo de como você pode fazer isso:

Instalar o snmpwalk:

sudo yum install net-snmp-utils
Executar o snmpwalk para explorar a MIB:

snmpwalk -v 2c -c public <IP_da_impressora> .1.3.6.1.2.1.43.11.1.1.9
Substitua <IP_da_impressora> pelo endereço IP da sua impressora. Isso deve listar todos os OIDs relacionados aos níveis de toner.

Se precisar de mais ajuda para usar o snmpwalk ou qualquer outra coisa, estou aqui para ajudar!