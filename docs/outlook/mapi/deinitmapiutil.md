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
ms.openlocfilehash: a9654efc34280941cdbc727bce9912a0a39d0fb9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427344"
---
# <a name="deinitmapiutil"></a>DeinitMapiUtil

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
释放由[ScInitMapiUtil](scinitmapiutil.md)函数显式或由[MAPIInitialize](mapiinitialize.md)函数隐式调用的实用工具函数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
VOID DeinitMapiUtil( void );
```

## <a name="parameters"></a>参数

无 
  
## <a name="return-value"></a>返回值

无 
  
## <a name="remarks"></a>说明

**DeinitMapiUtil**函数释放使用[ScInitMapiUtil](scinitmapiutil.md)或[MAPIInitialize](mapiinitialize.md)初始化的函数。 
  
在使用由**ScInitMapiUtil**调用的函数时, 必须显式调用**DeinitMapiUtil**以释放它们。 相比之下, [MAPIUninitialize](mapiuninitialize.md)隐式调用**DeinitMapiUtil**。 
  

