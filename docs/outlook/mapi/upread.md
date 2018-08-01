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
ms.openlocfilehash: fa3c0b90a64c90a7c854cb22ac75438fa5fca23f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779057"
---
# <a name="upread"></a>UPREAD

  
  
**适用于**： Outlook 
  
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

