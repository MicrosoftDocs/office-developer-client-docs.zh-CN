---
title: MSCAP_SELECTOR
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f28ac144-f5ac-fd83-2b72-8d6e5fd74b6e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9c5d8ab5bbac91250f3b8c552ad891c62134526e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338673"
---
# <a name="mscapselector"></a>MSCAP_SELECTOR

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定要为存储区返回的功能。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef enum 
{ 
    MSCAP_SEL_RESERVED1 = 0, 
    MSCAP_SEL_RESERVED2, 
    MSCAP_SEL_FOLDER, 
    MSCAP_SEL_RESERVED3, 
    MSCAP_SEL_RESTRICTION, 
} MSCAP_SELECTOR;
```

## <a name="members"></a>成员

 *MSCAP_SEL_RESERVED1* 
  
> 此成员是为内部使用 Outlook 而保留的, 不受支持。 
    
 *MSCAP_SEL_RESERVED2* 
  
> 此成员是为内部使用 Outlook 而保留的, 不受支持。 
    
 *MSCAP_SEL_FOLDER* 
  
> 有关在 store 上支持文件夹的功能。
    
 *MSCAP_SEL_RESERVED3* 
  
> 此成员是为内部使用 Outlook 而保留的, 不受支持。 
    
 *MSCAP_SEL_RESTRICTION* 
  
> 有关对存储区的支持限制的功能。
    

