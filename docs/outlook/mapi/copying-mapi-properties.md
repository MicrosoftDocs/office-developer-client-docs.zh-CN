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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415045"
---
# <a name="copying-mapi-properties"></a>复制 MAPI 属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端和服务提供商可以使用以下 **IMAPIProp** 方法和 API 函数复制对象的一个或多个属性： 
  
- [IMAPIProp：：CopyTo](imapiprop-copyto.md)方法将对象的所有属性复制到另一个对象，可以选择排除所选属性。 **CopyTo** 用于复制或移动任何类型的对象。 
    
- [IMAPIProp：：CopyProps](imapiprop-copyprops.md)方法复制对象的选定属性。 **CopyProps** 主要用于邮件。 当客户端创建邮件或回复的转发副本时 **，CopyProps** 处理从原始邮件复制相应属性。 
    
- [PropCopyMore](propcopymore.md)函数将单个属性值从一个位置复制到另一个位置。 请 **谨慎使用 PropCopyMore。** 在一次复制一个值时，可能会分配许多小的内存块，并会导致内存碎片化。 
    
- [ScCopyProps](sccopyprops.md)函数批量复制属性值。 **ScCopyProps** 可以复制从脱节的内存块构建的属性值。 它返回一个新的属性数组。 
    
- 如果 **ScCopyProps** 返回的属性数组要存储在磁盘上，请使用 [ScRelocProps](screlocprops.md) 函数调整指针。 **应调用两次 ScRelocProps;** 一次，在写入数据操作之前调整地址，然后在读取操作期间再次调整。 **ScRelocProps** 函数假定属性值数组最初在单个分配中分配。 
    
上述列表中描述的 API 函数将属性复制到内存中，而不是从一个对象复制到另一个对象。 这些函数目前受支持，但可能在未来版本中不受支持。
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

