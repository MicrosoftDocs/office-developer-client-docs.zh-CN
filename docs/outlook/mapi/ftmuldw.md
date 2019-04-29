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
  
将未签名的64位整数乘以无符号的32位整数。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
FILETIME FtMulDw(
  DWORD Multiplier,
  FILETIME Multiplicand
);
```

## <a name="parameters"></a>参数

 _乘以_
  
> 实时包含未签名的32位整数乘数的双字。 
    
 _Multiplicand_
  
> 实时一个[FILETIME](filetime.md)结构, 其中包含_乘_号参数中的值要乘以的无符号64位整数。 
    
## <a name="return-value"></a>返回值

**FtMulDw**函数返回一个**FILETIME**结构, 其中包含两个整数的乘积。 这两个输入参数保持不变。 
  

