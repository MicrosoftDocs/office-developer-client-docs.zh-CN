---
title: 网关映射职责
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ac67bb83-e4f3-4c82-995b-c11a2a195e90
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 91c1d9293108b96fde43b769c97ec673f82a8cb7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563028"
---
# <a name="gateway-mapping-responsibilities"></a>网关映射职责

**适用于**： Outlook 2013 |Outlook 2016 
  
当 MAPI 感知的网关接收邮件，包含名为属性指定用来包含网关可映射属性的特殊属性集之一时，该网关应将的所有属性映射到目标邮件系统的协议。 尽管 MAPI 建议网关处理中的特殊属性集的所有命名的属性，应网关处理只有两： 电子邮件地址和地址类型。 电子邮件地址和地址类型属性直接影响消息传输，因为它非常重要的网关支持这两个属性的映射。 因为搜索键包含用户的地址类型和地址，他们还应如果可能翻译。
  
条目标识符不会经常处理。 若要启用映射到可由另一个消息系统使用的项标识符的一个邮件系统中的项标识符，该网关必须能够使用两个系统的格式。 因为大多数网关不识别条目标识符格式，条目标识符的翻译很少见。
  
不需要经常转换的另一个可映射属性的显示名称。 网关应存储的显示名称和传输，但不是一定翻译。 
  

