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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356642"
---
# <a name="transmitting-and-copying-named-properties"></a>传输和复制命名属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
只要发送、移动或复制命名的属性, 名称将保持不变, 但标识符必须更改以符合目标对象的映射。 此规则的唯一例外是当源和目标具有相同的映射签名时, 再进行不必要的映射。
  
传输提供程序负责将已传输的命名属性的名称重新映射到在目标上工作的相应标识符。 发送传输提供程序无法知道目标是正确的映射。它必须传输名称, 并依靠接收的传输提供程序将它们映射到工作的标识符。 TNEF 的 MAPI 实现处理传输提供程序的命名属性的重映射。 传输提供程序既可以手动处理重新映射, 也可以使用 TNEF 实现。 
  
当在邮件存储之间复制这些属性时, 必须进行类似的命名属性重新映射。 但是, 由于邮件存储提供程序可以检索名称以映射目标的标识符, 因此可以立即重新映射属性, 而不必依赖目标邮件存储。 
  
## <a name="see-also"></a>另请参阅



[MAPI 命名属性](mapi-named-properties.md)

