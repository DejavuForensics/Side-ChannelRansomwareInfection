# Side-ChannelRansomwareInfection
Side-Channel Ransomware Infection

# US-EN:


# PT-BR:
## Infecção Lateral por Ransomware
 
O ransomware se consolidou como a principal ameaça no cenário de malwares (malicioso + softwares). Trata-se de um programa maliciosas capaz de se propagar por redes internas (intranets) com surpreendente facilidade e pouco esforço operacional. Sua atuação representa um grave risco à segurança da informação, pois tem o poder de extorquir vítimas e paralisar serviços essenciais, afetando desde agências governamentais até grandes corporações. Em regra geral, o modus operandi desse tipo de ataque consiste em criptografar os dados da vítima, tornando-os inacessíveis, e, na sequência, exigir o pagamento de um resgate em moedas digitais, como Bitcoin ou Monero, em troca da suposta restauração das informações comprometidas.
Uma das características mais perigosas de certos ransomwares é a propagação lateral. Isso significa que, ao infectar uma única máquina, o malware consegue se mover autonomamente pela intranet. Como consequência, o ataque escala rapidamente, dando ao ransomware a capacidade de sequestrar e criptografar os dados de toda a rede de uma instituição, e não apenas do dispositivo inicialmente comprometido.

No presente experimento, é empregado o NotPetya, um malware classificado superficialmente como ransomware, mas que na verdade atua como um wiper (destruidor de dados) de alta complexidade. Diferente dos ransomwares tradicionais, que visam o lucro financeiro através de uma criptografia reversível, o NotPetya é uma ferramenta projetada para sabotagem cibernética e industrial.
A tela de resgate exibida para a vítima é, na verdade, uma fachada. O seu suposto mecanismo de decriptação não possui a intenção de oferecer uma janela de recuperação ou restaurar os dados, mesmo que o pagamento do resgate seja realizado. Isso ocorre porque o malware não apenas criptografa os arquivos do usuário, mas sobrescreve dados do disco rígido. Essa ação torna a inicialização do sistema operacional e a recuperação dos dados matematicamente impossíveis.
O NotPetya foi desenvolvido para causar destruição em massa e interrupção de serviços críticos, causando danos irreversíveis à infraestrutura de uma instituição. Alinhado à sua capacidade de propagação lateral, ele se consolida como uma das ameaças mais destrutivas da história recente, operando muito além do simples propósito de extorsão financeira de um ransomware convencional.

## Ativar o modo promíscuo da interface de rede no Sniffer (Kali Linux)

No terminal, siga as seguinte etapas no Sniffer (Kali Linux).
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

