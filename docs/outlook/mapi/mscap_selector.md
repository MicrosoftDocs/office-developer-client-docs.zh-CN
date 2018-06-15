---
title: MSCAP_SELECTOR
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f28ac144-f5ac-fd83-2b72-8d6e5fd74b6e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 420b2661e766ecf97a5e9e488e9c18f29cd91329
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19776514"
---
# <a name="mscapselector"></a>MSCAP_SELECTOR

  
  
**适用于**： Outlook 
  
指定要返回的存储区的功能。
  
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
  
> 此成员仅供内部使用的 Outlook，不支持。 
    
 *MSCAP_SEL_RESERVED2* 
  
> 此成员仅供内部使用的 Outlook，不支持。 
    
 *MSCAP_SEL_FOLDER* 
  
> 有关对存储支持文件夹的功能。
    
 *MSCAP_SEL_RESERVED3* 
  
> 此成员仅供内部使用的 Outlook，不支持。 
    
 *MSCAP_SEL_RESTRICTION* 
  
> 有关对存储支持限制的功能。
    

