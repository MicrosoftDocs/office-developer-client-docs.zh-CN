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
ms.openlocfilehash: b8c70c8b13025f196fdebb2956939bec840a96f5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583937"
---
# <a name="sizedsrowset"></a>SizedSRowSet

**适用于**： Outlook 2013 |Outlook 2016 
  
创建命名的[SRowSet](srowset.md)结构，其中包含指定的行数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的结构：  <br/> |**SRowSet** <br/> |
   
```cpp
SizedSRowSet (_crow, _name)
```

## <a name="parameters"></a>参数

__crow_
  
> 要包含的新结构中的行数的计数。
    
__名称_
  
> 新结构的的名称。
    
## <a name="remarks"></a>注解

若要使用新结构的结果从**SizedSRowSet**宏作为指针指向**SRowSet**结构，执行下列转换： 
  
```cpp
lpSRowSet = (LPSRowSet) &SizedSRowSet;

```

## <a name="see-also"></a>另请参阅

- [SRowSet](srowset.md)
- [与结构相关的宏](macros-related-to-structures.md)

