# RESET EXPLODE — atribuição

Copyright (c) 2026 Gustavo (GustavoReset). Licença MIT em LICENSE.txt.

Origem: https://github.com/GustavoReset/ResetExplode
Revisão consultada: ce1d9b30518bbe75bb5e6cb792d1b1e365aaddd6 (26/10/2026).

Os getters adicionais de potência/P-state e a tolerância a funções opcionais em
src/AthyBoost.Hardware/Native/Nvml.cs foram adaptados de Nvml.cs, blob
c120d399950bb2e5576fe5c779373b22e59e3db7. Somente funções de leitura foram aproveitadas.

Os cartões de saúde de disco e GPU inspiram-se no RESET EXPLODE. A coleta de
armazenamento usa APIs do Windows e foi implementada sobre a arquitetura do
AthyBoost; não inclui LibreHardwareMonitor, PawnIO, funções de overclock nem
manipulação de memória de processos.

A MIT autoriza uso, modificação e redistribuição, inclusive comercial. Ao distribuir
as partes aproveitadas, preserve copyright, permissão e isenção de garantia
integrais. Ela não exige publicar o código do AthyBoost nem licenciar o app inteiro
sob MIT. Este aviso atribui as partes de terceiros e não muda a licença do restante
do projeto. Não implica parceria ou endosso de GustavoReset.

O build inclui LICENSE.txt e este arquivo no pacote; o Studio também permite ler
a licença em /licenses. Preserve estes arquivos em redistribuições.
