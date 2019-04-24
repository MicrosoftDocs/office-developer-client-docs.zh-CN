---
title: 复制 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a52f4bcd-6e17-4623-a469-53be1f2758b1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ae8e553cf2e19ae1ba06ca09aad84eae9f7d1238
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32333073"
---
# <a name="copying-mapi-properties"></a>复制 MAPI 属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端和服务提供程序可以使用以下**IMAPIProp**方法和 API 函数复制一个或多个对象的属性: 
  
- [IMAPIProp:: CopyTo](imapiprop-copyto.md)方法将对象的所有属性复制到另一个对象, 也可以选择排除选定的属性。 **CopyTo**用于复制或移动任何类型的对象。 
    
- [IMAPIProp:: CopyProps](imapiprop-copyprops.md)方法复制对象的选定属性。 **CopyProps**主要用于邮件。 当客户端创建转发的邮件副本或答复时, **CopyProps**将处理原始邮件中的相应属性。 
    
- [PropCopyMore](propcopymore.md)函数将单个属性值从一个位置复制到另一个位置。 使用**PropCopyMore**时要谨慎。 在一次复制一个值时, 可以分配多个小型内存块并导致内存分段。 
    
- [ScCopyProps](sccopyprops.md)函数批量复制属性值。 **ScCopyProps**可以从分离的内存块复制已生成的属性值。 它返回一个新的属性数组。 
    
- 如果**ScCopyProps**返回的属性数组要存储在磁盘上, 请使用[ScRelocProps](screlocprops.md)函数调整指针。 应调用**ScRelocProps**两次;在写入数据操作之前调整地址, 然后在读取操作过程中再次进行。 **ScRelocProps**函数假定属性值数组最初是在单个分配中分配的。 
    
上述列表中所述的 API 函数可复制内存中的属性, 而不是从一个对象复制到另一个对象。 目前支持这些函数, 但在将来的版本中可能不支持这些函数。
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

