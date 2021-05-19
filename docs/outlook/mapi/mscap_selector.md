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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417201"
---
# <a name="mscap_selector"></a>MSCAP_SELECTOR

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定为存储区返回的功能。
  
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
  
> 此成员仅供内部使用，Outlook不支持。 
    
 *MSCAP_SEL_RESERVED2* 
  
> 此成员仅供内部使用，Outlook不支持。 
    
 *MSCAP_SEL_FOLDER* 
  
> 有关在存储区上支持文件夹的功能。
    
 *MSCAP_SEL_RESERVED3* 
  
> 此成员仅供内部使用，Outlook不支持。 
    
 *MSCAP_SEL_RESTRICTION* 
  
> 有关对存储区的支持限制的功能。
    

