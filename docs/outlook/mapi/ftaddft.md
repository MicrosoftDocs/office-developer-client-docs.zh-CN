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
ms.openlocfilehash: e0e1535a770d4f1b437faf6a90c5f6415f6000ca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775012"
---
# <a name="ftaddft"></a>FtAddFt

  
  
**适用于**： Outlook 
  
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
  

