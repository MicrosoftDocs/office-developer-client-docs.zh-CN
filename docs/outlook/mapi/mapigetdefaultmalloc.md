---
title: MAPIGetDefaultMalloc
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPIGetDefaultMalloc
api_type:
- HeaderDef
ms.assetid: 148695dd-d886-4a06-9cfe-749059ae91ed
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cb0630ba30f8d3d7ae38c165c5da60bbc12077c1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592330"
---
# <a name="mapigetdefaultmalloc"></a>MAPIGetDefaultMalloc

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
检索默认 MAPI 内存分配函数的地址。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
LPMALLOC MAPIGetDefaultMalloc( );
```

## <a name="parameters"></a>参数

无。 
  
## <a name="return-value"></a>返回值

**MAPIGetDefaultMalloc**函数对默认 MAPI 内存分配函数返回的指针。 
  

