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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410929"
---
# <a name="sizedsrowset"></a>SizedSRowSet

**适用于**：Outlook 2013 | Outlook 2016 
  
创建包含 [指定行数的命名 SRowSet](srowset.md) 结构。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关结构：  <br/> |**SRowSet** <br/> |
   
```cpp
SizedSRowSet (_crow, _name)
```

## <a name="parameters"></a>参数

_ _管理_
  
> 要包含在新结构中的行数的计数。
    
_ _name_
  
> 新结构的名称。
    
## <a name="remarks"></a>备注

若要使用由 **SizedSRowSet** 宏产生的新结构作为 **指向 SRowSet** 结构的指针，请执行以下转换： 
  
```cpp
lpSRowSet = (LPSRowSet) &SizedSRowSet;

```

## <a name="see-also"></a>另请参阅

- [SRowSet](srowset.md)
- [与结构相关的宏](macros-related-to-structures.md)

