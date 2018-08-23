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
ms.openlocfilehash: 4b02fc316001ae11d64988cc29d0e62e9adde55e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585582"
---
# <a name="ftaddft"></a>FtAddFt

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
添加到另一个无符号的 64 位整数。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
FILETIME FtAddFt(
  FILETIME Addend1,
  FILETIME Addend2
);
```

## <a name="parameters"></a>参数

 _Addend1_
  
> [in]包含的第一个无符号的 64 位整数，要添加的[FILETIME](filetime.md)结构。 
    
 _Addend2_
  
> [in]包含的第二个无符号的 64 位整数，要添加的**FILETIME**结构。 
    
## <a name="return-value"></a>返回值

**FtAddFt**函数将返回一个**FILETIME**结构，其中包含两个包含整数的总和。 两个输入的参数保持不变。 
  

