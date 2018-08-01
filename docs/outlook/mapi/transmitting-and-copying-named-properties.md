---
title: 传输和复制命名的属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 37075cfc-461d-4983-9045-d9f1da6739be
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a5d2244270463fcc2fe0a9786112590e741a8a66
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778994"
---
# <a name="transmitting-and-copying-named-properties"></a>传输和复制命名的属性

  
  
**适用于**： Outlook 
  
发送的命名的属性时，移动或复制，名称保持不变，但必须更改标识符遵守的目标对象映射。 对此规则唯一的例外是源和目标具有相同的映射签名时, 进行重新映射不必要。
  
是要重新映射到相应的标识符在目标工作的传输命名属性的名称的传输提供程序的责任。 发送传输提供程序无法知道什么正确映射是在目标;它必须传输名称，并依赖于接收的传输提供程序，以将其映射到工作的标识符。 TNEF 的 MAPI 实现处理传输提供程序将命名属性。 传输提供程序可以处理重新映射手动或使用 TNEF 实现。 
  
消息存储之间复制这些属性时，必须发生命名属性类似重新映射。 但是，因为消息存储提供程序可以检索到的目标的标识符映射的名称，他们可以立即重新映射属性，并不需要依赖目标消息存储区。 
  
## <a name="see-also"></a>另请参阅



[MAPI 命名属性](mapi-named-properties.md)

