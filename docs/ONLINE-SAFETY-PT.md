# Online experimental — construção, limites e segurança

**TER CUIDADO: abrir uma porta do roteador expõe o serviço do jogo à internet. O código da sala não criptografa a conexão. Não existe garantia de segurança absoluta.**

Este documento acompanha a versão **4.20 FPS experimental**, para Windows, Linux e Android. A cópia **4.20 estável** permanece separada. Os dois Read Mes originais não foram substituídos.

## Como o online foi construído

- O host executa a campanha e as simulações nativas dos jogadores. Os convidados enviam controles e recebem sua própria imagem, além dos comandos de áudio correspondentes.
- A mesma implementação atende computador e Android. Cada dispositivo mantém sua câmera e seu zoom; jogadores no mesmo dispositivo podem usar divisão de tela.
- Batalhas conjuntas utilizam as seleções simultâneas do COOP nativo. As regras e a resolução dos turnos continuam no host.
- A música é reproduzida pelo motor SPC/DSP local do convidado, conforme os comandos da sua situação no jogo. O modo online não acelera a música para ganhar FPS.
- O protocolo não oferece execução remota de comandos de sistema, transferência de ROMs, upload de arquivos ou envio de snapshots da memória nativa. Isso reduz a superfície exposta, mas não prova ausência de falhas.
- A base nativa é o trabalho de Brian Pugh e colaboradores de BrianPugh/earthbound. LakeSnes, SDL2 e outros projetos e colaboradores estão creditados em CREDITS.md e licenses/. A adaptação inclui trabalho de Edzito com assistência de IA/Codex. O online é experimental e não passou por auditoria independente de segurança.

## O que funciona como proteção

- Código de sala de seis dígitos, gerado com a fonte aleatória do sistema, e limite de tentativas por endereço.
- Limites para conexões pendentes, tamanhos de mensagens, filas, imagens e tempo de handshake/inatividade.
- Rejeição antecipada de tipos e comprimentos inválidos. Convidados enviam apenas handshake, entrada ou heartbeat nos formatos previstos.
- Limite de 240 mensagens completas por segundo por cliente e validação da sequência dos pacotes.
- CRC32 para detectar corrupção e validação dos limites ao descomprimir imagens. **CRC32 não é autenticação criptográfica.**
- Busca LAN sem publicar o código da sala, com respostas limitadas e filtragem de endereços locais/VPN. A descoberta não conecta ninguém automaticamente.
- O jogo não configura encaminhamento de portas no roteador automaticamente.

## LAN: cuidados práticos

Prefira uma rede doméstica confiável, com equipamentos atualizados e senha de Wi-Fi forte. Compartilhe o código somente com pessoas conhecidas. Uma pessoa conectada à mesma rede ainda pode observar ou interferir em tráfego sem criptografia, dependendo da rede.

Permita o aplicativo no firewall somente no perfil privado e, quando possível, limite o acesso à sub-rede local. Não desative o firewall inteiro para jogar. A busca LAN usa UDP, normalmente na porta 32176; a sessão usa TCP, normalmente na mesma porta. Confira a porta exibida no menu Online caso tenha sido alterada.

A descoberta contempla IPv4 privado, loopback, link-local, faixa compartilhada de VPN e endereços usados pelo Hamachi. Redes incomuns podem exigir IP/porta explícitos. As respostas UDP não devem ser encaminhadas para a internet.

## Internet e porta aberta: atenção redobrada

1. Prefira um túnel VPN confiável, configurado com criptografia, entre pessoas conhecidas. O jogo não cria esse túnel nem verifica a segurança do provedor.
2. Se optar por encaminhamento manual de porta, entenda que outras pessoas poderão tentar alcançar o serviço. Encaminhe somente o TCP necessário ao jogo; não exponha a descoberta UDP, a área de trabalho remota ou outros serviços junto.
3. Não publique IP, código da sala, capturas do menu de conexão ou arquivos de rede em locais públicos. Quem recebe uma imagem do jogo pode gravá-la.
4. Feche a hospedagem ao terminar. Remova também a regra de encaminhamento do roteador e permissões de firewall que não precisar mais: fechar o jogo não apaga regras criadas manualmente.
5. Use apenas builds de origem confiável. Não execute como administrador/root para contornar problemas de conexão. Faça backup dos saves antes de testar versões novas.

**Não há TLS, criptografia ponta a ponta, autenticação de identidade, certificado de servidor, anticheat ou proteção completa contra negação de serviço.** O código da sala controla a entrada; ele não protege contra um observador da rede. Este projeto não deve ser tratado como um servidor público endurecido.

## Desempenho e outras limitações

- O alvo de vídeo é até 60 FPS. A taxa real depende do host, GPU, telefone, áudio, número de jogadores e rede; 50 ou 60 FPS não são garantidos.
- A taxa de quadros recebidos e a renderização nativa são medidas separadamente. Quadros repetidos não devem ser apresentados como ganho real de renderização.
- A carga pesada fica no host. Atraso, perda de conexão, sinal Wi-Fi fraco e filas congestionadas podem reduzir fluidez ou resposta.
- A campanha inteira com todas as combinações de personagens não foi validada. Testes automatizados não substituem testes em celulares físicos ou entre redes reais.
- CGNAT, isolamento de clientes Wi-Fi, redes de convidados e regras de firewall podem impedir a conexão. O jogo não remove essas restrições automaticamente.
- Saves da sessão pertencem ao host. Faça cópias antes de trocar versões; não presuma que toda versão experimental tem compatibilidade irrestrita.

## Verificações locais desta versão

Os testes exercitam descoberta LAN sem revelar o código, código incorreto, tamanho excessivo, cabeçalho de transferência indevida e sequência inválida. Também comparam pixels de janelas, validam o codec/checksum e conferem batalhas, controles, zoom e áudio com processos separados. Esses testes não equivalem a uma auditoria independente, a um teste de invasão completo ou a uma garantia para redes reais.

Os avisos de entrada aparecem sobre a partida: “Jogador se conectando...” e “Conectado!”, com equivalentes em inglês.

## Se algo parecer errado

Desconecte, feche a hospedagem e preserve seus saves. Anote a versão, quantidade de jogadores, dispositivos e a ação que provocou o problema. Antes de compartilhar logs ou capturas, retire IPs, códigos da sala, nomes de usuário e caminhos pessoais. Não inclua ROMs nem chaves de assinatura.

Documento atualizado em 30/10/2026. Créditos e licenças completos: CREDITS.md e licenses/.
