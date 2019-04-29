---
title: FtAdcFt
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2635a829-0f3a-49ed-a672-2f350a2cf979
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f308c1f6f3cd2c9904dd94cd6761517bd5b410b6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429703"
---
# <a name="ftadcft"></a>FtAdcFt

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将一个无符号64位整数添加到另一个, 可以选择使用带有标志。
  
|||
|:-----|:-----|
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
FILETIME FtAdcFt( 
  FILETIME ft1, 
  FILETIME ft2, 
  WORD FAR *pwCarry
);
```

## <a name="parameters"></a>参数

 _ft1_
  
> 实时一个[FILETIME](filetime.md)结构, 其中包含要添加的第一个不带符号的64位整数。 
    
 _ft2_
  
> 实时一个 FILETIME 结构, 其中包含要添加的第二个带符号的64位整数。
    
 _pwCarry_
  
> [in、out、optional]在输入时, 指向传入的传输标志的指针。 在输出时, 指向添加项的承载结果的指针。 如果不需要 "执行" 结果, 则此参数可以为 NULL。
    
## <a name="return-value"></a>返回值

**FtAdcFt**函数返回一个**FILETIME**结构, 其中包含两个整数的和。 这两个输入参数保持不变。 如果**pwCarry**为非 NULL, 则它包含总和的包含结果, 即0或1。 
  
## <a name="remarks"></a>说明

当_pwCarry_为 NULL 时, **FtAdcFt**函数等同于**FtAddFt** 。 如果_pwCarry_不为 NULL, 并指向 0, 则**FtAdcFt**将返回**FtAddFt**返回的同一**FILETIME**值。 
  
## <a name="see-also"></a>另请参阅



[FtAddFt](ftaddft.md)

