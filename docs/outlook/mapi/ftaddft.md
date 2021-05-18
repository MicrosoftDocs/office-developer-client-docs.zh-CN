---
title: FtAddFt
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FtAddFt
api_type:
- COM
ms.assetid: 341ad06b-1caa-49bb-b859-cb512f6fb55d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cb20469adec938817fedf1b00789304625b388c8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404762"
---
# <a name="ftaddft"></a>FtAddFt

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将一个无符号 64 位整数添加到另一个整数。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
FILETIME FtAddFt(
  FILETIME Addend1,
  FILETIME Addend2
);
```

## <a name="parameters"></a>参数

 _Addend1_
  
> [in] [FILETIME](filetime.md) 结构，包含要添加的第一个无符号 64 位整数。 
    
 _Addend2_
  
> [in] **FILETIME** 结构，包含要添加的第二个无符号 64 位整数。 
    
## <a name="return-value"></a>返回值

**FtAddFt** 函数返回 **FILETIME** 结构，其中包含两个整数的总和。 两个输入参数保持不变。 
  

