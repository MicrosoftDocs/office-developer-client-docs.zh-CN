---
title: SizedENTRYID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedENTRYID
api_type:
- COM
ms.assetid: 491170af-db35-4d7e-a912-44ffe8c7506b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 88cf91330dea82dda490b81cc8de6fea0504baf7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405707"
---
# <a name="sizedentryid"></a>SizedENTRYID

**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个命名的[ENTRYID](entryid.md)结构, 其中包含指定大小的**ab**成员。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关结构:  <br/> |**ENTRYID** <br/> |
   
```cpp
SizedENTRYID (_cb, _name)
```

## <a name="parameters"></a>参数

__cb_
  
> 新结构的**ab**成员中的字节数。 
    
__名称_
  
> 新结构的名称。
    
## <a name="remarks"></a>说明

**SizedENTRYID**宏允许您在已知数组长度要求后定义条目标识符。 使用此宏创建具有显式界限的条目标识符。 
  
若要使用作为指向**ENTRYID**结构的指针的**SizedENTRYID**宏生成的新结构, 请执行以下转换: 
  
```cpp
lpENTRYID = (LPENTRYID) &SizedENTRYID;

```

## <a name="see-also"></a>另请参阅

- [ENTRYID](entryid.md)
- [与结构相关的宏](macros-related-to-structures.md)

