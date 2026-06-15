# Side-ChannelRansomwareInfection
Side-Channel Ransomware Infection

# US-EN:


# PT-BR:
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

