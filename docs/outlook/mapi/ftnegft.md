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
  
计算两个不带符号的64位整数的补码。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
FILETIME FtNegFt(
  FILETIME ft
);
```

## <a name="parameters"></a>参数

 _ft_
  
> 实时一个[FILETIME](filetime.md)结构, 其中包含为其计算两个补码的无符号64位整数。 
    
## <a name="return-value"></a>返回值

**FtNegFt**函数返回一个**FILETIME**结构, 其中包含整数的两个补码。 输入参数保持不变。 
  

