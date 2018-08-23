---
title: MEID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: aa8f18d9-691d-d0cc-a660-f15ea6cff6ce
description: 上次修改时间： 2012 年 7 月 3 日
ms.openlocfilehash: 24cc4b00f02c61395565fb7ddeb6a5b5a62afdc5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591938"
---
# <a name="meid"></a>MEID

 
  
**适用于**： Outlook 2013 |Outlook 2016 
  
某个 Outlook 项目的的标识符。 它包含的项标识符以及其他相关信息。
  
## <a name="quick-info"></a>快速信息

```cpp
struct MEID 
{ 
    BYTE abFlags[4]; 
    MAPIUID muid; 
    WORD placeholder; 
    LTID ltidFld; 
    LTID ltidMsg; 
};
```

## <a name="members"></a>Members

 _abFlags_
  
> 对 Outlook 项目的 4 字节条目标识符。 有关 MAPI 项标识符的详细信息，请参阅**[ENTRYID](entryid.md)**。 
    
 _muid_
  
> 标识的存储提供程序的 GUID。 请参阅 mapidefs.h **MAPIUID**的类型定义。 
    
 _占位符_
  
> 此成员仅供内部使用的 Outlook，不支持。
    
 _ltidFld_
  
> 文件夹的长期 ID。
    
 _ltidMsg_
  
> Outlook 项目的长期 ID。
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[LTID](ltid.md)
  
[SYNC](sync.md)
  
[UPMSG](upmsg.md)

