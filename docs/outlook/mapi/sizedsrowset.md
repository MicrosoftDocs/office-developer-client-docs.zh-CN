---
title: SizedSRowSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedSRowSet
api_type:
- COM
ms.assetid: 419e2c6d-ac3b-46c6-9a12-33f51f6d7f12
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cb1e19a3f3703dc4943a5f6c322f1c8b429da5fa
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282640"
---
# <a name="sizedsrowset"></a>SizedSRowSet

**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个包含指定数量的行的命名[SRowSet](srowset.md)结构。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关结构:  <br/> |**SRowSet** <br/> |
   
```cpp
SizedSRowSet (_crow, _name)
```

## <a name="parameters"></a>参数

__鱼尾纹_
  
> 要包含在新结构中的行数的计数。
    
__名称_
  
> 新结构的名称。
    
## <a name="remarks"></a>注解

若要使用作为指向**SRowSet**结构的指针的**SizedSRowSet**宏生成的新结构, 请执行以下转换: 
  
```cpp
lpSRowSet = (LPSRowSet) &SizedSRowSet;

```

## <a name="see-also"></a>另请参阅

- [SRowSet](srowset.md)
- [与结构相关的宏](macros-related-to-structures.md)

