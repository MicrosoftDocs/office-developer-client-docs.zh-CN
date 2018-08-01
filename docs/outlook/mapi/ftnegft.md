---
title: FtNegFt
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FtNegFt
api_type:
- COM
ms.assetid: 639a408c-aed1-456b-9f75-9d6fb8dcb33b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e26acb8415df007a7f3fb5901521da7222ae40ed
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775020"
---
# <a name="ftnegft"></a>FtNegFt

  
  
**适用于**： Outlook 
  
计算 2 的补充的无符号的 64 位整数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
FILETIME FtNegFt(
  FILETIME ft
);
```

## <a name="parameters"></a>参数

 _ft_
  
> [in][FILETIME](filetime.md)结构，其中包含要计算的 2 的补充无符号的 64 位整数。 
    
## <a name="return-value"></a>返回值

**FtNegFt**函数将返回一个**FILETIME**结构，其中包含 2 的补充的整数。 输入的参数保持不变。 
  

