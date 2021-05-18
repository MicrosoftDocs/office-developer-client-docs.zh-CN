---
title: FtSubFt
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FtSubFt
api_type:
- COM
ms.assetid: 6619fc41-5518-44ce-85c1-6b0077ed5cb9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: edd789a586adc71289ff821aa7cf7a33f79fb738
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408416"
---
# <a name="ftsubft"></a>FtSubFt

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将一个无符号 64 位整数从另一个整数中减去。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
FILETIME FtSubFt(
  FILETIME Minuend,
  FILETIME Subtrahend
);
```

## <a name="parameters"></a>参数

 _Minuend_
  
> [in]包含无符号 64 位整数的 [FILETIME](filetime.md) 结构，将从该整数中减去  _Subtrahend_ 参数中的值。 
    
 _Subtrahend_
  
> [in]包含无符号 64 位整数的 **FILETIME** 结构，该整数从  _Minuend_ 参数指示的值中减去。 
    
## <a name="return-value"></a>返回值

**FtSubFt** 函数返回包含减法结果的 **FILETIME** 结构。 两个输入参数保持不变。 
  

