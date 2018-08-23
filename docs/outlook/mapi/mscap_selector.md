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
ms.openlocfilehash: 8c23788d64fe3703c7c46998cade0bd40d2f3dd2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588123"
---
# <a name="mscapselector"></a>MSCAP_SELECTOR

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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

## <a name="members"></a>Members

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
    

