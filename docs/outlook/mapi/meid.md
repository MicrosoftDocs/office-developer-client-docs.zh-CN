---
title: MEID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: aa8f18d9-691d-d0cc-a660-f15ea6cff6ce
description: 上次修改时间：2012 年 7 月 3 日
ms.openlocfilehash: a9aea0db700de9c82aa2a41a443ebf03da8ce9b3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430306"
---
# <a name="meid"></a>MEID

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
项目标识符Outlook项。 它包含条目标识符和其他相关信息。
  
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

## <a name="members"></a>成员

 _abFlags_
  
> 项目项的 4 字节Outlook标识符。 有关 MAPI 条目标识符详细信息，请参阅 **[ENTRYID](entryid.md)**。 
    
 _muid_
  
> 标识存储提供程序的 GUID。 有关 **MAPIUID** 的类型定义，请参阅 mapidefs.h。 
    
 _占位符_
  
> 此成员仅供内部使用，Outlook不支持。
    
 _ltidFld_
  
> 文件夹的长期 ID。
    
 _ltidMsg_
  
> 项目的长期 ID Outlook ID。
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[LTID](ltid.md)
  
[SYNC](sync.md)
  
[UPMSG](upmsg.md)

