---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: ad4f2cc3b03111854d10d6a1c1128f090a629a07
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490967"
---
# <a name="mtommessageencodingbindingelement"></a>MtomMessageEncodingBindingElement
MtomMessageEncodingBindingElement  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Métodos  
 A classe MtomMessageEncodingBindingElement não define quaisquer métodos.  
  
## <a name="properties"></a>Propriedades  
 A classe MtomMessageEncodingBindingElement tem as seguintes propriedades:  
  
### <a name="encoding"></a>Codificando  
 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O conjunto de caracteres codificação a ser usada para emitir mensagens na associação.  
  
### <a name="maxreadpoolsize"></a>MaxReadPoolSize  
 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 Um inteiro que define quantas mensagens pode ser lidas simultaneamente sem alocar novos leitores.  
  
### <a name="maxwritepoolsize"></a>MaxWritePoolSize  
 Tipo de dados: sint32  
  
 Tipo de acesso: Somente leitura  
  
 Um inteiro que define quantas mensagens pode ser enviado simultaneamente sem alocar novos escritores.  
  
### <a name="readerquotas"></a>ReaderQuotas  
 Tipo de dados: XmlDictionaryReaderQuotas  
  
 Tipo de acesso: Somente leitura  
  
 As cotas dos leitores.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definido no root\ServiceModel|  
  
## <a name="see-also"></a>Consulte também
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
