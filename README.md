# Configurando-Recursos-e-Dimensionamentos-em-M-quinas-Virtuais-na-Azure
Contéudo do Treinamento Configurando Recursos e Dimensionamentos em Máquinas Virtuais na Azure Microsoft Azure Essentials DIO 

Tópico 1 - O que são Máquinas Virtuais do Azure?

As VMs do Azure permitem aos usuários criar e gerenciar máquinas virtuais dentro da infraestrutura do Azure. Essencialmente, são computadores virtuais que operam em servidores físicos na rede global da Microsoft. Essas VMs podem ser personalizadas com diferentes tamanhos, sistemas operacionais, e configurações.

Vantagens:

1. Flexibilidade : Escolha entre uma variedade de tamanhos e opções de VM para atender às suas necessidades.
2. Escalabilidade : Expanda ou reduza facilmente sua infraestrutura de acordo com a demanda.
3. Integração : As VMs do Azure se integram facilmente com outros serviços do Azure, como o Azure Active Directory e o Azure Blob Storage.
4. Segurança : Beneficie-se dos protocolos de segurança da Microsoft, garantindo que suas VMs estejam protegidas.

Os conjuntos de dimensionamento de Máquinas Virtuais facilitam a criação de aplicativos altamente escalonáveis, permitindo implantar e gerenciar sem esforço um conjunto de VMs como um grupo. Baseados no modelo de implantação do Azure Resource Manager, os conjuntos de dimensionamento de VMs são totalmente integrados ao balanceamento de carga e ao dimensionamento automático do Azure e são compatíveis com Windows, Linux, imagens personalizadas e extensões. Os conjuntos de dimensionamento de VMs oferecem dois modos de operação:

VMs de Conjunto de Dimensionamento: fornecem fácil criação e gerenciamento de VMs idênticas
VMs únicas: fornecem uma maneira fácil de adicionar suas VMs ao VMSS durante o processo de criação (como para obter alta disponibilidade)
Os conjuntos de dimensionamento de Máquinas Virtuais estão disponíveis atualmente em todos os tamanhos de VMs do Azure do Windows ou do Linux. Você será cobrado somente pelas VMs do Azure implantadas, bem como quaisquer recursos adicionais de infraestrutura subjacente consumidos, como armazenamento e rede. Não há encargos incrementais para o serviço de conjuntos de dimensionamento de Máquinas Virtuais. Aplicam-se encargos de saída padrão.

Abaixo segue o link para Preços do Conjuntos de dimensionamento de máquina virtual 

https://azure.microsoft.com/pt-br/pricing/details/virtual-machine-scale-sets

Obs.: Os preços são apenas estimativas e não pretendem ser cotações de preços reais. O preço real pode variar dependendo do tipo de contrato celebrado com a Microsoft, data de compra e taxa de câmbio. Os preços são calculados com base em dólares americanos e convertidos usando as taxas spot de fechamento de Londres capturadas nos dois dias úteis anteriores ao último dia útil do final do mês anterior. Se os dois dias úteis anteriores ao final do mês caírem em um feriado bancário nos principais mercados, o dia de definição da taxa geralmente é o dia imediatamente anterior aos dois dias úteis.

Segue o link abaixo do Seletor de máquinas virtuais (Encontre as VMs certas para suas necessidades e seu orçamento)

https://azure.microsoft.com/pt-br/pricing/vm-selector/

Tópico 2 - Criar uma máquina virtual do Windows no portal do Azure:

As máquinas virtuais do Azure (VMs) podem ser criadas através do portal do Azure. Este método fornece uma interface de utilizador baseada no browser para criar VMs e os respetivos recursos associados. Este guia de início rápido mostra como usar o portal do Azure para implantar uma máquina virtual (VM) no Azure que executa o Windows Server 2019. Para ver a VM em ação, estabeleça o RDP para a VM e instale o servidor Web IIS.

1ª Etapa - Insira máquinas virtuais na pesquisa;

2ª Etapa - Em Serviços, selecione Máquinas virtuais;

3ª Etapa - Na página Máquinas virtuais, selecione Criar e, em seguida, Máquina virtual do Azure. A página Criar uma máquina virtual é aberta;

4ª Etapa - Em Detalhes da instância, insira myVM para o nome da máquina virtual e escolha Windows Server 2022 Datacenter: Azure Edition - x64 Gen 2 para a imagem. Mantenha as restantes predefinições inalteradas. Em detalhes da instância onde você fornece um nome para a máquina virtual e seleciona sua região, imagem e tamanho;
Obs.: Para saber mais sobre esse novo recurso, consulte "Criar máquinas virtuais em uma zona de disponibilidade". 

5ª Etaṕa - Em Conta de administrador, forneça um nome de utilizador, como utilizadordoazure, e uma palavra-passe. A palavra-passe tem de ter, pelo menos, 12 carateres e cumprir os requisitos de complexidade definidos. Conta de administrador fornece o nome de utilizador e palavra-passe(senha) de administrador (importante guardar/memorizar login e senha criados):

6ª Etapa - Em Regras de porta de entrada, escolha Permitir portas selecionadas e, em seguida, selecione RDP (3389) e HTTP (80) na lista suspensa. A seção de regras de porta de entrada, é onde você seleciona quais portas as conexões de entrada são permitidas;

7ª Etapa - Mantenha as restantes predefinições e, em seguida, selecione o botão Rever + criar na parte inferior da página. botão Rever(REVIEW) + criar(CREATE) na parte inferior da página:

8ª Etapa - Após a execução da validação, selecione o botão Criar na parte inferior da página. Captura de ecrã a mostrar que a validação foi aprovada. Selecione o botão Criar para criar a VM;

9ª Etapa - Após a conclusão da implantação, selecione Ir para o recurso;

Tópico 3 - Connect to virtual machine (Ligar à máquina virtual)

Crie uma ligação de ambiente de trabalho remoto para a máquina virtual. Estas instruções indicam como ligar à VM a partir de um computador Windows. Num Mac, precisa de um cliente RDP como este Cliente de Ambiente de Trabalho Remoto a partir da Mac App Store.

1ª Etapa - Na página de visão geral da sua máquina virtual, selecione Conectar >RDP. 

2ª Etapa - Na guia Conectar com RDP, mantenha as opções padrão para se conectar por endereço IP, pela porta 3389, e clique em Baixar arquivo RDP.

3ª Etapa - Abra o ficheiro RDP transferido e clique em Ligar quando lhe for pedido.

4ª Etapa - Na janela Segurança do Windows, selecione Mais escolhas e Utilizar uma conta diferente. Digite o nome de usuário como nome de usuário localhost\, digite a senha criada para a máquina virtual e clique em OK.

5ª Etapa - Poderá receber um aviso de certificado durante o processo de início de sessão. Clique em Sim ou Continuar para criar a ligação.

6ª Etapa - Após a mensagem de certificado validada, na inicialização do RDP, aguardar surgir a tela de login e inserir login e senha informados no momento da criação da VM

7ª Etapa - Após o processo de acesso, vocẽ terá acesso a máquina virtaul e poderá iniciar suas operações na máquina de acordo com seus estudos

