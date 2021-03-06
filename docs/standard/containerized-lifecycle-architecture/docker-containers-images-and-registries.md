---
title: Registros, imagens e contêineres do Docker
description: Saiba o papel importante que registros desempenham gerais na maneira como Docker de implantação de aplicativos.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 7a2e20e09561a5cc91aa29059fb8d19a14205bb5
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221193"
---
# <a name="docker-containers-images-and-registries"></a>Registros, imagens e contêineres do Docker

Ao usar o Docker, você cria um aplicativo ou serviço e o empacota com suas dependências em uma imagem de contêiner. Uma imagem é uma representação estática do aplicativo ou do serviço e de sua configuração e dependências.

Para executar o aplicativo ou o serviço, uma instância da imagem do aplicativo é criada para criar um contêiner, que estará em execução no host do Docker. Inicialmente, os contêineres são testados em um ambiente de desenvolvimento ou em um computador.

Armazenar imagens em um registro, que atua como uma biblioteca de imagens. Você precisa de um registro ao implantar em orquestradores de produção. O Docker mantém um Registro público por meio do [Hub do Docker](https://hub.docker.com/); outros fornecedores fornecem os Registros para diferentes coleções de imagens. Como alternativa, as empresas podem ter um Registro privado local para suas próprias imagens do Docker.

Figura 1-4 mostra como imagens e registros no Docker se relacionam com outros componentes. Ela também mostra as várias ofertas de Registro dos fornecedores.

![](./media/image4.png)

Figura 1-4: Taxonomia de termos e conceitos do Docker

Ao colocar imagens em um registro, você pode armazenar os bits de aplicativo estáticos e imutáveis, incluindo todas as suas dependências, em um nível de framework. Você pode a versão e implantar imagens em vários ambientes, em seguida e, portanto, fornecem uma unidade de implantação consistente.

Registros de imagem privados, hospedados localmente ou na nuvem, são recomendados para as seguintes situações:

-   Suas imagens não devem ser compartilhadas publicamente devido à confidencialidade.

-   Você deseja ter latência de rede mínima entre suas imagens e o ambiente de implantação escolhido. Por exemplo, se seu ambiente de produção é o Azure, você provavelmente desejará armazenar as imagens no registro de contêiner do Azure para que a latência de rede seja mínima. De maneira semelhante, se seu ambiente de produção for local, tenha um Registro Confiável do Docker local disponível na mesma rede local.

>[!div class="step-by-step"]
>[Anterior](docker-terminology.md)
>[Próximo](road-to-modern-applications-based-on-containers.md)
