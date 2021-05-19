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
ms.openlocfilehash: db208dad8697060e394b3ee037ea658cefbab669
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423382"
---
# <a name="ftnegft"></a>FtNegFt

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
计算无符号 64 位整数的二者的补充。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
FILETIME FtNegFt(
  FILETIME ft
);
```

## <a name="parameters"></a>参数

 _ft_
  
> [in] [FILETIME](filetime.md) 结构，包含要计算二者的补充的无符号 64 位整数。 
    
## <a name="return-value"></a>返回值

**FtNegFt** 函数返回 **FILETIME** 结构，其中包含两个整数的补数。 输入参数保持不变。 
  

