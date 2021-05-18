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
ms.openlocfilehash: 54561450e7d91d8a30695dacf508758623547e39
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412910"
---
# <a name="ftmuldwdw"></a>FtMulDwDw

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将一个无符号 32 位整数乘以另一个。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
FILETIME FtMulDwDw(
  DWORD Multiplicand,
  DWORD Multiplier
);
```

## <a name="parameters"></a>参数

 _Multiplicand_
  
> [in]包含要乘以  _乘_ 数参数中的值的无符号 32 位整数的双词。 
    
 _乘数_
  
> [in]包含无符号 32 位整数乘数的双词。
    
## <a name="return-value"></a>返回值

**FtMulDwDw** 函数返回 [FILETIME](filetime.md)结构，其中包含两个整数的乘数。 两个输入参数保持不变。 
  

