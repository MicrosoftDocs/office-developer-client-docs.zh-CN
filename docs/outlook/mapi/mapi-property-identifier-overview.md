---
title: MAPI 属性标识符概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 957aa00f-23d8-4f3b-bbc2-7d54f17b47b5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 29626f49365a0f37f1e13d965c62bfd5ad0fb774
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414695"
---
# <a name="mapi-property-identifier-overview"></a>MAPI 属性标识符概述

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
属性标识符是一个数字，用于指示属性用于什么以及由谁负责。 属性标识符按 MAPI 划分到范围中;其中标识符属于范围，指示其使用和所有权。 
  
属性标识符的范围从 0x0001 到 0xFFFF。 所有情况下0x0000和0xFFFF保留属性标识符，这意味着这些标识符必须保持未使用状态。 MAPI 定义的属性范围从 0x0001 到 0x3FFF。 这些属性称为 MAPI 定义的属性。 要0x4000 0x7FFF属于邮件和收件人属性，客户端或服务提供商都可以定义此范围中的属性。 要访问0x0001 0x7FFF属性称为标记属性。 除了 0x8000 是所谓的命名属性的范围，或者是包括 32 位全局唯一标识符 (GUID) 以及 Unicode 字符串或数值的属性。 客户端可以使用命名属性自定义其属性集。
  
服务提供商可以在范围中定义安全配置文件属性，0x67F0到0x67FF。 安全配置文件属性用于需要额外保护的信息，如密码。 这些属性可以隐藏和加密。 [IMAPIProp：：GetPropList](imapiprop-getproplist.md)方法返回的属性的默认列表中是否包含安全属性取决于提供程序的实现。 通常不包括这些属性。 [IProfSect ： IMAPIProp](iprofsectimapiprop.md)接口用于访问配置文件节的属性，包括安全属性。 
  
某些属性范围仅限于可传输属性或非可传输属性。 可传输属性随邮件一起传输;不可传输的属性不会随邮件一起传输。 不可传输的属性通常包含仅对使用当前会话的客户端和服务提供商有价值的信息。 这些属性不一定对另一个邮件系统和另一组服务提供商有用。 可传输属性的概念主要适用于传输提供程序。 若要确定属性是否可传输，请传递其属性标记到 **FIsTransmittable** 宏，该宏在 Mapitags.h 头文件中定义。 
  
有关标识符范围的完整说明，请参阅 [属性标识符范围](property-identifier-ranges.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

