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
ms.openlocfilehash: c823a4e3d08d9082a3b5ac5c4bd8169612caa16e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583993"
---
# <a name="ftmuldw"></a>FtMulDw

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
相乘 32 位无符号整数无符号的 64 位的整数。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
FILETIME FtMulDw(
  DWORD Multiplier,
  FILETIME Multiplicand
);
```

## <a name="parameters"></a>参数

 _乘子_
  
> [in]双字包含 32 位无符号的整数乘数。 
    
 _被乘数_
  
> [in]一个[FILETIME](filetime.md)结构包含无符号的 64 位整数，若要相乘的_乘数_参数中的值。 
    
## <a name="return-value"></a>返回值

**FtMulDw**函数将返回一个**FILETIME**结构，其中包含两个包含整数的产品。 两个输入的参数保持不变。 
  

