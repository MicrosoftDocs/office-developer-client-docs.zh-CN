---
title: DeinitMapiUtil
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- DeinitMapiUtil
api_type:
- HeaderDef
ms.assetid: e0b8dc9c-cc46-4d27-9497-7a55a0bfdff5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e84dbc0976f5c438a7e0b5fd7cddcbf1c0659f40
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574795"
---
# <a name="deinitmapiutil"></a>DeinitMapiUtil

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
释放由[ScInitMapiUtil](scinitmapiutil.md)函数或隐式[MAPIInitialize](mapiinitialize.md)函数显式调用的实用工具函数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
   
```cpp
VOID DeinitMapiUtil( void );
```

## <a name="parameters"></a>参数

无 
  
## <a name="return-value"></a>返回值

无 
  
## <a name="remarks"></a>注解

初始化与[ScInitMapiUtil](scinitmapiutil.md)或[MAPIInitialize](mapiinitialize.md) **DeinitMapiUtil**函数版本函数。 
  
使用由**ScInitMapiUtil**调用的函数完成后， **DeinitMapiUtil**必须明确调用其发布。 相比之下， [MAPIUninitialize](mapiuninitialize.md)隐式调用**DeinitMapiUtil**。 
  

