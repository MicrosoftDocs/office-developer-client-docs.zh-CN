---
title: UPREAD
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 568f2336-cb4d-3f2c-a304-d29cdb0bcbcc
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 887c66277b54e2e14c7f67c76b8e9dd4fa8bc719
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589229"
---
# <a name="upread"></a>UPREAD

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
用于[上载读取状态状态](upload-read-status-state.md)期间上载读取的项的状态信息。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPREAD 
{ 
    PUPREADE pupre; 
    UINT cEnt; 
};
```

## <a name="members"></a>Members

 _pupre_
  
>  [输出]**[UPREADE](upreade.md)** 条目的向量。 
    
 _%_
  
>  [输出]**UPREADE**条目数。 
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[MAPI 常量](mapi-constants.md)
  
[UPREADE](upreade.md)

