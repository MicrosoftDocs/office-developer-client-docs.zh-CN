---
title: FtMulDw
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FtMulDw
api_type:
- COM
ms.assetid: e135ba67-97be-4ce0-a72e-93c49ed7d6e2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 27ec919d720e1089d6e102f20485d936c9dc9808
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406344"
---
# <a name="ftmuldw"></a>FtMulDw

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
无符号 64 位整数乘以无符号 32 位整数。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
FILETIME FtMulDw(
  DWORD Multiplier,
  FILETIME Multiplicand
);
```

## <a name="parameters"></a>参数

 _乘数_
  
> [in]包含无符号 32 位整数乘数的双词。 
    
 _Multiplicand_
  
> [in] [FILETIME](filetime.md) 结构，包含要乘以  _乘_ 数参数中的值的无符号 64 位整数。 
    
## <a name="return-value"></a>返回值

**FtMulDw** 函数返回 **FILETIME** 结构，其中包含两个整数的乘数。 两个输入参数保持不变。 
  

