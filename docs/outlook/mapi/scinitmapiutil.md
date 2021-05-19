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
ms.openlocfilehash: 090a73ed908d2a647d00de27b93538a77766c258
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420589"
---
# <a name="scinitmapiutil"></a>ScInitMapiUtil

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
仅在使用选择实用程序函数时替换[MAPIInitialize。](mapiinitialize.md) 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
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
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

**ScInitMapiUtil** 和 [DeinitMapiUtil](deinitmapiutil.md)函数共同调用和释放选择实用工具函数，而不是调用核心函数和实用程序函数的 [MAPIInitialize](mapiinitialize.md)函数。 当 **ScInitMapiUtil** 调用实用程序函数时，它还初始化必要的内存。 
  
使用 **ScInitMapiUtil** 调用的函数完成后，必须显式调用 **DeinitMapiUtil** 以释放它们。 相比之下 **，MAPIInitialize** 隐式调用 **DeinitMapiUtil**。 
  
## <a name="see-also"></a>另请参阅



[MAPIUninitialize](mapiuninitialize.md)

