---
title: 复制的 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a52f4bcd-6e17-4623-a469-53be1f2758b1
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2f9ee7221f523d7c92d91746f5cd719fad821a27
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774711"
---
# <a name="copying-mapi-properties"></a>复制的 MAPI 属性

  
  
**适用于**： Outlook 
  
客户端和服务提供商可以复制一个或多个对象的属性，与以下**IMAPIProp**方法和 API 函数： 
  
- [IMAPIProp::CopyTo](imapiprop-copyto.md)方法将所有对象的属性复制到另一个对象，可选择不包括所选的属性。 **CopyTo**用于复制或移动任何类型的对象。 
    
- [IMAPIProp::CopyProps](imapiprop-copyprops.md)方法将复制所选的对象的属性。 **CopyProps**主要用于消息。 当客户端创建一份转发的邮件或回复， **CopyProps**处理从原始邮件复制的相应属性。 
    
- [PropCopyMore](propcopymore.md)函数将从一个位置的单个属性值复制到另一个。 请谨慎使用**PropCopyMore** 。 可能 — 一次复制的一个值时 — 分配内存的许多小型块，并导致内存片段。 
    
- [ScCopyProps](sccopyprops.md)函数批量复制属性值。 **ScCopyProps**可从内存脱节块复制已生成的属性值。 它返回新的属性数组。 
    
- 如果返回**ScCopyProps**属性数组是存储在磁盘上，使用[ScRelocProps](screlocprops.md)函数调整指针。 应两次; 调用**ScRelocProps**一次在写入数据操作之前调整地址，然后再次期间读取操作。 **ScRelocProps**函数假定属性值数组中的单个分配原来分配给。 
    
上述列表副本属性在内存中，而不是从另一个对象的一个对象中描述的 API 功能。 这些函数目前支持，但可能不受支持的将来版本中。
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

