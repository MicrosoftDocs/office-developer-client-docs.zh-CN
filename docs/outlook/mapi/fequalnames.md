---
title: FEqualNames
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FEqualNames
api_type:
- COM
ms.assetid: 4dd58b0b-dc39-4782-a9ec-05e353c90927
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0d8d1b8509f699b20f6e436d8af2c1d0d97cf4ba
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774917"
---
# <a name="fequalnames"></a>FEqualNames

  
  
**适用于**： Outlook 
  
确定两个 MAPI 命名属性是否相同。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
BOOL FEqualNames(
  LPMAPINAMEID lpName1,
  LPMAPINAMEID lpName2
);
```

## <a name="parameters"></a>参数

 _lpName1_
  
> [in]指向[MAPINAMEID](mapinameid.md)结构描述的第一个命名的属性。 
    
 _lpName2_
  
> [in]指向**MAPINAMEID**结构描述第二个命名的属性。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 两个属性名称相等。 
    
FALSE 
  
> 两个属性名称不相等。
    
## <a name="remarks"></a>说明

**FEqualNames**函数很有用，因为**MAPINAMEID**结构包含[GUID](guid.md) ，并可以表示多种方式中的属性名称本身。 这意味着不能由简单二进制方法比较两个结构。 
  
区分大小写的属性名称字符串的测试过程。 
  

