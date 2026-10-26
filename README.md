<p align="center"><img src="docs/logo.png" width="100" alt="Logo AthyBoost"></p>

# AthyBoost

**Monitoramento de hardware, painéis para Echo Show e ajustes reversíveis do Windows.**

Desenvolvido por **Athirson Lamonato Ferreira**. Este é o repositório público de distribuição: downloads, notas de versão e documentação. O código-fonte principal é mantido em um repositório privado.

[Baixar AthyBoost.exe](https://github.com/AthirsonLamonato/AthyBoost-Releases/releases/latest/download/AthyBoost.exe) · [Todas as releases](https://github.com/AthirsonLamonato/AthyBoost-Releases/releases) · [LinkedIn](https://www.linkedin.com/in/athirsonlamonato/) · [Contato](mailto:athirson.lamonato@gmail.com)

## O que o aplicativo oferece

| Recurso | Como funciona |
| --- | --- |
| Hardware ao vivo | CPU, GPU, RAM, VRAM, disco e rede, com sensores disponíveis no Windows e no driver de vídeo. |
| GPU detalhada | Em placas NVIDIA compatíveis: temperatura, clocks, consumo, limite de potência, P-state e motivos de limite de clock, apenas por leitura NVML. |
| Saúde dos discos | Estado informado pelo Windows, temperatura, desgaste, horas ligado e erros quando o dispositivo e as permissões permitem. |
| Painéis / Echo Show | Editor com blocos móveis e redimensionáveis, cores, fontes, sete modelos prontos e transmissão na rede local. |
| Alertas e gráficos | Limites visuais configuráveis e gráficos de 1, 5 ou 10 minutos, mantidos na memória da página. |
| Meu PC e Check-up | Inventário de componentes, relatório e verificações de saúde do sistema. |
| Otimizações e Game Boost | Ajustes com descrição e valor original guardado; configurações por jogo e alterações de sessão reversíveis. |
| Ferramentas | Inicialização, limpeza, manutenção, instalação de aplicativos, testes de rede, mouse e monitor. |
| Overlay opcional | Janela própria com estatísticas de desempenho; medição de frames via PresentMon, sem injeção no jogo. |
| Histórico e Recovery | Consulta das alterações e restauração dos valores originais. |

O AthyBoost não promete ganho de FPS. Cada ajuste depende do computador, do Windows, do jogo e das configurações em uso.

## Requisitos

- Windows 10 ou Windows 11, **64 bits**.
- O executável portátil inclui o runtime .NET; não é necessário instalar o SDK.
- Microsoft Edge WebView2 Runtime para o editor integrado dos painéis.
- PC e Echo na mesma rede para usar o painel pelo Amazon Silk.
- Sensores NVIDIA dependem do driver e do suporte da placa. Em outros fabricantes, parte das leituras pode ficar indisponível.

O monitoramento básico pode funcionar sem administrador. Ajustes do sistema e determinados sensores de armazenamento podem exigir elevação. A temperatura da CPU não é lida quando exige um driver de kernel adicional; o AthyBoost não instala esse driver.

## Baixar e começar

1. Abra a [release mais recente](https://github.com/AthirsonLamonato/AthyBoost-Releases/releases/latest).
2. Baixe **AthyBoost.exe** e confira as notas daquela versão.
3. Abra o executável. A edição portátil extrai seus componentes em `%LOCALAPPDATA%\AthyBoost\portable`.
4. Use as telas de monitoramento ou leia a descrição de cada ajuste antes de aplicá-lo.

Na versão portátil, `AthyBoost.Service.exe` pode funcionar como processo auxiliar do usuário. Isso é diferente de instalar um serviço do Windows. Fechar a janela pode manter o servidor dos painéis ativo se você habilitou essa opção.

Os executáveis ainda não têm assinatura digital do autor. Confira a origem do download e o SHA-256 publicado nas notas da release. Não desative proteções do Windows para executar o programa.

## Configurar o Echo Show

1. No AthyBoost, abra **Painéis / Echo Show**.
2. Monte sua tela livremente ou escolha um dos modelos: Visão geral, CPU em destaque, GPU em destaque, GPU detalhada, Compacto, Rede e disco ou Saúde e temperaturas.
3. Ative a transmissão e copie o **endereço mostrado pelo seu próprio PC**.
4. No Echo, abra o navegador Silk, acesse esse endereço e digite o código exibido no AthyBoost.
5. Personalize pelo PC. O Echo recebe a visualização do painel ativo.

Não existe IP pessoal embutido no aplicativo. Endereços de rede, caminhos de usuário e credenciais de pareamento são obtidos ou gerados em cada computador. A porta padrão do painel é **TCP 8755**. Se o roteador mudar o IP do PC, atualize o endereço aberto no Silk.

O Echo preserva as funções da Alexa. Tela cheia e permanência do Silk dependem do navegador e do firmware do dispositivo; não há garantia de funcionamento como quiosque permanente. O modo experimental **Manter aberto** tenta evitar o retorno à tela inicial.

### Continuar depois de fechar a janela

Marque **Continuar em segundo plano ao fechar** se quiser manter o painel funcionando. O computador precisa continuar ligado, acordado e conectado à rede. O painel não passa a funcionar na nuvem nem coleta sensores de um PC desligado.

**Iniciar ao entrar no Windows** é opcional. Use **Encerrar servidor** no app para parar a transmissão e a coleta do painel.

### Atualizar uma versão anterior

Feche a janela antiga e abra o novo executável. Se o servidor anterior ainda estiver em segundo plano, use **Encerrar servidor**, **Reabrir servidor**, reabra o editor e atualize a página no Silk. Os layouts salvos permanecem na pasta de dados do usuário.

## Entender as leituras

- Campo indisponível aparece sem dados; o aplicativo não inventa uma temperatura ou porcentagem de saúde.
- O estado do disco informado pelo Windows não garante ausência de falhas. Desgaste não prevê uma data de defeito.
- P-state, repouso e limite de potência são informações do driver. Um limite de potência reportado não significa, sozinho, falha de hardware.
- Os limites de alerta são configuráveis. Use valores adequados aos seus componentes.
- O histórico dos gráficos dos painéis fica na memória da página; não grava uma sessão de diagnóstico.

## Dados e privacidade

Preferências, layouts e dados do usuário ficam em `%LOCALAPPDATA%\AthyBoost`. Alterações feitas em modo elevado podem usar `%PROGRAMDATA%\AthyBoost` para o journal e os registros do serviço.

O painel transmite sensores e layouts na rede local, protegido por pareamento. Ele não expõe os comandos de otimização. O código de acesso pertence à instalação do próprio usuário; não vem com credenciais do desenvolvedor.

Os ajustes guardam seus valores originais antes da aplicação. Para desfazê-los, use **Histórico → Restaurar tudo** ou o **Recovery** disponível nas configurações. Apagar arquivos do programa não restaura automaticamente ajustes que já foram aplicados ao Windows.

## Jogos e anticheats

O overlay é opcional e usa uma janela separada. As estatísticas de frames usam PresentMon. Compatibilidade e regras de anticheat variam: o AthyBoost não é homologado por todos os fornecedores e não oferece garantia contra punições de terceiros.

## Sugestões e suporte

Descreva o que aconteceu, qual versão você usa e o resultado esperado. Não envie senhas, tokens ou arquivos pessoais desnecessários.

- **E-mail:** [athirson.lamonato@gmail.com](mailto:athirson.lamonato@gmail.com)
- **LinkedIn:** [Athirson Lamonato Ferreira](https://www.linkedin.com/in/athirsonlamonato/)
- **GitHub:** [AthirsonLamonato](https://github.com/AthirsonLamonato)

## Histórico de versões

Consulte as [releases públicas](https://github.com/AthirsonLamonato/AthyBoost-Releases/releases) para baixar versões, ler alterações, limitações e validações realizadas. Use a versão mais recente como padrão; versões anteriores ficam disponíveis apenas como histórico.
