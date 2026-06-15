# Side-ChannelRansomwareInfection
Side-Channel Ransomware Infection

# US-EN:


# PT-BR:
## Infecção Lateral por Ransomware
 
O ransomware se consolidou como a principal ameaça no cenário de malwares (malicioso + softwares). Trata-se de um programa maliciosas capaz de se propagar por redes internas (intranets) com surpreendente facilidade e pouco esforço operacional. Sua atuação representa um grave risco à segurança da informação, pois tem o poder de extorquir vítimas e paralisar serviços essenciais, afetando desde agências governamentais até grandes corporações. Em regra geral, o modus operandi desse tipo de ataque consiste em criptografar os dados da vítima, tornando-os inacessíveis, e, na sequência, exigir o pagamento de um resgate em moedas digitais, como Bitcoin ou Monero, em troca da suposta restauração das informações comprometidas.

### Siga as instruções
No terminal, siga as seguinte etapas no Sniffer (Kali Linux).

## Ativar o modo promíscuo da interface de rede no Sniffer (Kali Linux)

O comando a seguir instrui o NetworkManager a não gerenciar a interface `eth0`. Isso evita que o Kali Linux, por ora, não interfira na topologia da intranet durante a captura de pacotes.
```
nmcli device set eth0 managed no
```

Desativação temporária da interface eth0 de modo a permitir alterações de configuração com segurança.
```
ip link set eth0 down
```

Remoção de todosassociado à interface eth0, isolando o sniffer na camada 2 (camada de enlace).
```
ip addr flush dev eth0
```

Ativação do modo promíscuo e, simultaneamente, reativação da interface eth0 novamente em estado ativo.
```
ip link set eth0 promisc on up
```

Exibição do status e as configurações atuais da interface para confirmar as alterações.
```
ip addr show eth0
```

## Configura o IP nas máquinas que serão infectadas

## Ativar o Switch 

