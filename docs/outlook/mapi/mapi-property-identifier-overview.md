---
title: MAPI 属性标识符概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 957aa00f-23d8-4f3b-bbc2-7d54f17b47b5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8cf2f08a69ee87c40789b764596e514c91483c2e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563154"
---
# <a name="mapi-property-identifier-overview"></a>MAPI 属性标识符概述

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
属性标识符是一个数字，用于指示属性用于和谁负责执行它。 属性标识符可以分为若干通过 MAPI 范围;标识符属于范围中的其中指示其使用情况和所有权。 
  
属性标识符的范围从 0x0001 经过 0xFFFF。 在所有情况下，这意味着，这些标识符必须保持未使用保留 0x0000 和 0xFFFF 属性标识符。 定义的 MAPI 属性的范围从 0x0001 运行，以 0x3FFF。 这些属性被称为自定义 MAPI 的属性。 范围 0x4000 到 0x7FFF 所属消息和收件人属性，并且客户端或服务提供商可以在此范围中定义属性。 0x0001 到 0x7FFF 范围中的属性称为带标记的属性。 超出 0x8000 是被称为命名的属性或包含 32 位的全局唯一标识符 (GUID) 和 Unicode 字符串或数值的属性的范围。 客户端可以使用命名的属性自定义其属性集。
  
服务提供商可以定义范围通过 0x67FF 0x67F0 中的安全配置文件属性。 安全配置文件属性用于需要额外的保护，如密码的信息。 这些属性可以隐藏和加密。 由[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法返回的属性的默认列表中包含安全属性取决于提供程序的实现。 通常不包括这些属性。 [IProfSect: IMAPIProp](iprofsectimapiprop.md)接口用于访问配置文件部分，包括安全属性的属性。 
  
某些属性区域被限制为可传送属性或 nontransmittable 属性。 一条消息; 会传输可传送属性一条消息，不会传输 nontransmittable 属性。 Nontransmittable 属性通常包含的值仅为客户端和操作系统与当前会话的服务提供商的信息。 这些属性不一定是另一个邮件系统和服务提供商的另一组有用。 可传送属性的概念主要于传输提供程序。 若要确定是否可传送属性，请将其属性标记传递给**FIsTransmittable**宏，Mapitags.h 标头文件中定义。 
  
标识符范围的完整说明，请参阅[属性标识符范围](property-identifier-ranges.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

