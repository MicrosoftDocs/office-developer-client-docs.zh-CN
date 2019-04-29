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
  
属性标识符是一个数字, 用于指示属性的用途和负责的所有者。 将属性标识符除以 MAPI 到区域中;其中, 标识符位于范围内表示其使用和所有权。 
  
属性标识符的范围从0x0001 到0xffff 运行。 在所有情况下都会保留属性标识符0x0000 和 0xffff, 这意味着这些标识符必须保持未使用。 MAPI 定义的属性的范围从0x0001 运行到0x3FFF。 这些属性称为 MAPI 定义的属性。 0x4000 到0x7FFF 的范围属于邮件和收件人属性, 客户端或服务提供程序可以在此范围内定义属性。 0x0001 到0x7FFF 的范围中的属性称为 "标记属性"。 大于0x8000 是指称为命名属性的范围, 或者是包含32位全局唯一标识符 (GUID) 的属性, 也可以是 Unicode 字符字符串或数值。 客户端可以使用命名属性来自定义其属性集。
  
服务提供程序可以在0x67F0 到0x67FF 的范围内定义安全配置文件属性。 安全配置文件属性用于需要其他保护的信息, 如密码。 可以对这些属性进行隐藏和加密。 [IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法返回的默认属性列表中是否包含安全属性？: 方法取决于提供程序的实现。 通常情况下, 这些属性不包括在内。 [IProfSect: IMAPIProp](iprofsectimapiprop.md)接口用于访问配置文件部分的属性, 包括安全属性。 
  
某些属性范围限制为传输属性或 nontransmittable 属性。 传输属性与邮件一起传输;nontransmittable 属性不会与邮件一起传输。 Nontransmittable 属性通常包含仅对在当前会话中运行的客户端和服务提供程序具有价值的信息。 这些属性不一定对其他邮件系统和另一组服务提供商有用。 传输属性的概念主要适用于传输提供程序。 若要确定某个属性是否为传输, 请将其 property 标记传递给 Mapitags 头文件中定义的**FIsTransmittable**宏。 
  
有关标识符范围的完整说明, 请参阅[属性标识符范围](property-identifier-ranges.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

