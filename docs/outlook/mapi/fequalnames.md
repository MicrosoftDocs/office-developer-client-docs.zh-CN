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
ms.openlocfilehash: 8f71b30bd02af8f768da86218456feadda8ea1b6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414800"
---
# <a name="fequalnames"></a>FEqualNames

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
确定两个 MAPI 命名属性是否相同。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
BOOL FEqualNames(
  LPMAPINAMEID lpName1,
  LPMAPINAMEID lpName2
);
```

## <a name="parameters"></a>参数

 _lpName1_
  
> [in]指向描述第一个命名属性的 [MAPINAMEID](mapinameid.md) 结构的指针。 
    
 _lpName2_
  
> [in]指向描述第二个命名属性的 **MAPINAMEID** 结构的指针。 
    
## <a name="return-value"></a>返回值

TRUE 
  
> 两个属性名称相等。 
    
FALSE 
  
> 这两个属性名称不相等。
    
## <a name="remarks"></a>备注

**FEqualNames** 函数很有用，因为 **MAPINAMEID** 结构包含 [GUID，](guid.md)并且可以通过多个方式表示属性名称本身。 这意味着无法通过简单的二进制方法比较这两种结构。 
  
对于属性名称字符串，测试过程区分大小写。 
  

