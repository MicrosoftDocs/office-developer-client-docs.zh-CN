---
title: 传输和复制命名属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 37075cfc-461d-4983-9045-d9f1da6739be
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6534e7344a62717e406c112249d26407b0852d93
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437775"
---
# <a name="transmitting-and-copying-named-properties"></a>传输和复制命名属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
每当发送、移动或复制命名属性时，名称将保持不变，但必须更改标识符，以遵守目标对象的映射。 此规则的唯一例外是源和目标具有相同的映射签名，因此不需要重新映射。
  
传输提供程序负责将传输的命名属性的名称重新映射为在目标处工作的适当标识符。 发送传输提供程序无法知道目标的正确映射是什么;它必须传输名称并依赖接收传输提供程序将它们映射到工作的标识符。 TNEF 的 MAPI 实现处理传输提供程序的命名属性的重新映射。 传输提供程序可以手动处理重新映射或使用 TNEF 实现。 
  
在邮件存储之间复制命名属性时，必须发生类似的命名属性重新映射。 但是，由于邮件存储提供程序可以检索到目标标识符映射的名称，因此它们可以马上重新映射属性，而不需要依赖目标邮件存储。 
  
## <a name="see-also"></a>另请参阅



[MAPI 命名属性](mapi-named-properties.md)

