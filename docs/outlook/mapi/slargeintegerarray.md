---
title: SLargeIntegerArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SLargeIntegerArray
api_type:
- COM
ms.assetid: 9ec9a674-c1a2-4137-856f-6cabe6f0eb9f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ab82fff2645a5e1861523eb3f1866e0ddc7d13a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331386"
---
# <a name="slargeintegerarray"></a>SLargeIntegerArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个 [LARGE_INTEGER](https://go.microsoft.com/fwlink/?LinkId=132130) 结构数组，用于描述类型为 PT_MV_I8。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _SLargeIntegerArray
{
  ULONG cValues;
  LARGE_INTEGER FAR *lpli;
} SLargeIntegerArray;

```

## <a name="members"></a>Members

 **cValues**
  
> lpli 成员指向的数组中的值计数。 
    
 **lpli**
  
> 指向包含整数 **值的LARGE_INTEGER** 数组的指针。 
    
## <a name="remarks"></a>备注

有关属性类型PT_MV_18，请参阅 [属性类型列表](property-types.md)。
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

