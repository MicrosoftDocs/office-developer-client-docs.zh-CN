---
title: ScInitMapiUtil
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ScInitMapiUtil
api_type:
- HeaderDef
ms.assetid: d83b8ea8-a3b8-4038-a226-de1869c5d722
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 771b466e58bf57a7eb4285c6f6ce94c815ec7288
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778693"
---
# <a name="scinitmapiutil"></a>ScInitMapiUtil

  
  
**适用于**： Outlook 
  
当正在使用仅选择实用工具函数替换[MAPIInitialize](mapiinitialize.md) 。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
   
```cpp
SCODE ScInitMapiUtil(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

**ScInitMapiUtil**和[DeinitMapiUtil](deinitmapiutil.md)函数共同呼叫并释放选择实用工具函数，而不是[MAPIInitialize](mapiinitialize.md)，后者核心以及实用程序函数。 当**ScInitMapiUtil**调用实用工具函数时，它还初始化所需的内存。 
  
使用的呼叫**ScInitMapiUtil**函数完成后， **DeinitMapiUtil**必须明确调用其发布。 相比之下， **MAPIInitialize**隐式调用**DeinitMapiUtil**。 
  
## <a name="see-also"></a>另请参阅



[MAPIUninitialize](mapiuninitialize.md)

