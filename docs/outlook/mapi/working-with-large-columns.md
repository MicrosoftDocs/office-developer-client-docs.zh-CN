---
title: 处理大型列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 452acccf-22fd-4450-b50f-eaa2b2c94515
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a191a8551d425d7e8b3b9a281936a4a0e2dfd587
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779089"
---
# <a name="working-with-large-columns"></a>处理大型列

  
  
**适用于**： Outlook 
  
列中的包含字符串或二进制属性数据可能很大，可能数千个字节长。 视图中包括一个或多个列与数百个字节通常是不切实际的因为 MAPI 使表实施者截断的值，最常到 255 个字节和 510 字节越来越少。 只要有可能，表实施应包括的表格列中的属性的完整值。 建议使用的替代是包含前 255 个字节。
  
客户端无法事先知道，他们使用的表是否截断大型列。 他们应假定列表示截断的属性，如果列的长度为 255 个或 510 字节。 如有必要，客户端可以直接截断列的完整值从对象中检索通过调用该对象的[IMAPIProp::GetProps](imapiprop-getprops.md)方法。 
  
构建具有大型属性限制的客户端应注意，最多为表实施来如何这些限制对操作。 某些表实施允许使用截断列时其他人基于整个值基于截断大小生成的限制。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

