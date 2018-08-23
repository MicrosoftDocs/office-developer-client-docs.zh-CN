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
ms.openlocfilehash: f073dbb9655585ee56ab38be35bea4ef320042c0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569769"
---
# <a name="ftadcft"></a>FtAdcFt

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
向另一个，（可选） 使用携带标志添加一个无符号的 64 位整数。
  
|||
|:-----|:-----|
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
FILETIME FtAdcFt( 
  FILETIME ft1, 
  FILETIME ft2, 
  WORD FAR *pwCarry
);
```

## <a name="parameters"></a>参数

 _ft1_
  
> [in]包含的第一个无符号的 64 位整数，要添加的[FILETIME](filetime.md)结构。 
    
 _ft2_
  
> [in]包含的第二个无符号的 64 位整数，要添加的 FILETIME 结构。
    
 _pwCarry_
  
> [传入、 传出，可选]在输入时，指向传入的执行标志。 在输出，指向增加的执行结果的指针。 如果要结果，则不需要此参数可以是 NULL。
    
## <a name="return-value"></a>返回值

**FtAdcFt**函数将返回一个**FILETIME**结构，其中包含两个包含整数的总和。 两个输入的参数保持不变。 如果**pwCarry**为非 NULL，则它包含的执行结果 sum、 0 或 1。 
  
## <a name="remarks"></a>注解

**FtAdcFt**函数等同于**FtAddFt** _pwCarry_为 NULL 时。 如果_pwCarry_不为 NULL，并指向 0， **FtAdcFt**返回**FtAddFt**返回的同一个**FILETIME**值。 
  
## <a name="see-also"></a>另请参阅



[FtAddFt](ftaddft.md)

