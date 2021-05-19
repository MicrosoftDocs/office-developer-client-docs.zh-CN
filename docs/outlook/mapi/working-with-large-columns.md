---
title: 使用大列
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
# <a name="working-with-large-columns"></a>使用大列

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
具有字符串或二进制属性数据的列可能很大，可能数千字节长。 由于在视图中包含一个或多个包含数百个字节的列通常不切实际，因此 MAPI 允许表实现程序截断值，通常截断为 255 字节，而将更不常截断为 510 字节。 只要有可能，表实施者应在表列中包括属性的完整值。 建议的替代项是仅包含前 255 个字节。
  
客户端无法提前知道他们使用的表是否截断了大列。 如果列的长度为 255 或 510 字节，则它们应假定列代表截断的属性。 如有必要，客户端可以通过调用对象的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法直接从对象检索截断列的完整值。 
  
使用大型属性构建限制的客户端应注意，这些限制的运行方式由表实施者决定。 某些表实现程序允许使用截断列构建的限制基于截断的大小，而其他表实现器则基于整个值。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

