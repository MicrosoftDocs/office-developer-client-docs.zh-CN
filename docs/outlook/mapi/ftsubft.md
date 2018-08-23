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
ms.openlocfilehash: ad561bd3be7fd0c9f25c11875f62667563dfcbe7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578260"
---
# <a name="ftsubft"></a>FtSubFt

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
剪除与从另一个无符号的 64 位整数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
FILETIME FtSubFt(
  FILETIME Minuend,
  FILETIME Subtrahend
);
```

## <a name="parameters"></a>参数

 _被减数_
  
> [in][FILETIME](filetime.md)结构，包含从中_减数_参数中的值是中减去的 64 位无符号的整数。 
    
 _减数_
  
> [in]**FILETIME**结构，其中包含从指示_被减数_参数的值减去的无符号的 64 位整数。 
    
## <a name="return-value"></a>返回值

**FtSubFt**函数将返回包含结果的减法**FILETIME**结构。 两个输入的参数保持不变。 
  

