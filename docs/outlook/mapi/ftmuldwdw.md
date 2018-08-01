---
title: FtMulDwDw
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FtMulDwDw
api_type:
- COM
ms.assetid: 8c1a342c-d7ae-4e26-b327-a63cdd3c3ee6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 16dca82b94225afc88bcb6c4e698a50565d6b088
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775009"
---
# <a name="ftmuldwdw"></a>FtMulDwDw

  
  
**适用于**： Outlook 
  
另一个乘以一个无符号的 32 位整数。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
FILETIME FtMulDwDw(
  DWORD Multiplicand,
  DWORD Multiplier
);
```

## <a name="parameters"></a>参数

 _被乘数_
  
> [in]双字包含 32 位无符号的整数相乘的_乘数_参数中的值。 
    
 _乘子_
  
> [in]双字包含 32 位无符号的整数乘数。
    
## <a name="return-value"></a>返回值

**FtMulDwDw**函数将返回一个[FILETIME](filetime.md)结构，其中包含两个包含整数的产品。 两个输入的参数保持不变。 
  

