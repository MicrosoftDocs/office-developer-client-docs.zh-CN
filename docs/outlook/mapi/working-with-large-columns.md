---
title: 处理大型列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 452acccf-22fd-4450-b50f-eaa2b2c94515
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9ca3c5e7a0d1b4a6ac09dcfcc7db10ec76ecb224
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420421"
---
# <a name="working-with-large-columns"></a>处理大型列

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
带有字符串或二进制属性数据的列可能会很大, 可能很多包含数千个字节。 由于在视图中包含包含数百个字节的一个或多个列通常是不切实际的, 因此 MAPI 使表实施者能够将此值截断, 最常见的是255字节, 而频率不到510字节。 只要有可能, 表实施者就应将属性的完整值包括在表的列中。 建议的替代方法是仅包含前255个字节。
  
客户端无法提前知道其使用的表是否截断了大型列。 如果列的长度为255或510字节, 则用户应假定列表示截断的属性。 如果需要, 客户端可以通过调用对象的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法直接从对象中检索截断的列的完整值。 
  
使用大型属性构建限制的客户端应注意, 对于表实施者来说, 这些限制是如何运行的。 某些表实施者允许使用被截断的列生成的限制基于截断的大小, 而另一些则将其作为整个值。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

