# resumo-do-lab
Usar a ação de logon do Azure com OpenID Connect

Para configurar um logon do Azure com o OpenID Connect e usá-lo em um fluxo de trabalho do GitHub Actions, você precisará de:

    Um aplicativo Microsoft Entra, com uma entidade de serviço que foi atribuída com uma função apropriada à sua assinatura.
    Um aplicativo Microsoft Entra configurado com uma credencial federada para confiar em tokens emitidos por Ações do GitHub para seu repositório do GitHub. Você pode configurar isso no portal do Azure ou com APIs REST do Microsoft Graph.
    Um fluxo de trabalho de Ações do GitHub que solicita tokens de emissão do GitHub para o fluxo de trabalho e usa a ação de logon do Azure.

Criar um aplicativo e uma entidade de serviço do Microsoft Entra

Você precisará criar um aplicativo e uma entidade de serviço do Microsoft Entra e, em seguida, atribuir uma função em sua assinatura ao seu aplicativo para que seu fluxo de trabalho tenha acesso à sua assinatura.

    Portal do Azure
    CLI do Azure
    PowerShell do Azure

    Se você não tiver um aplicativo existente, registre um novo aplicativo e entidade de serviço do Microsoft Entra que possa acessar recursos. Como parte desse processo, é necessário:
        Registre seu aplicativo com o Microsoft Entra ID e crie uma entidade de serviço
        Atribuir uma função ao aplicativo

    Selecionar o aplicativo em Registros de aplicativo no portal do Azure e encontrar o aplicativo. Copiar os valores de ID do Aplicativo (cliente) e de ID do Diretório (locatário) para serem usados no fluxo de trabalho do GitHub Actions.

    Abrir Assinaturas no portal do Azure e encontrar sua assinatura. Copie a ID da assinatura.

Adicionar credenciais federadas

Você pode adicionar credenciais federadas no portal do Azure ou com a API REST do Microsoft Graph.

    Portal do Azure
    CLI do Azure
    PowerShell do Azure

    Acesse Registros de aplicativo no portal do Azure e abra o aplicativo que você deseja configurar.
    No aplicativo, acesse Certificados e segredos.
    Select Certificates & secrets.
    Na guia Credenciais federadas, selecione Adicionar credencial. Add the federated credential
    Selecione o cenário de credencial GitHub Actions implantando recursos do Azure. Gere sua credencial inserindo os detalhes dela.
