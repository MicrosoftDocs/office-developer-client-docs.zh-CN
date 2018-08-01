---
title: HDRSYNC
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: bf6892d0-a923-e926-5361-59efa49ebdc0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: bd1c327eb2042957c8fb043736950af3dae520b7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775073"
---
# <a name="hdrsync"></a>HDRSYNC

  
  
**适用于**： Outlook 
  
同步过程中[下载邮件头状态](download-message-header-state.md)的邮件头信息。
  
## <a name="quick-info"></a>快速信息

```cpp
struct HDRSYNC 
{ 
    UPMSG *pupmsg; 
    FEID feidPar; 
    LPSTREAM pstmReserved; 
    ULONG ulFlags; 
    LPMESSAGE pmsgFull; 
};
```

## <a name="members"></a>Members

 _pupmsg_
  
- [输出]本地存储中的当前邮件头信息。
    
 _feidPar_
  
- [输出]邮件项目的父文件夹的条目 ID。
    
 _pstmReserved_
  
- [输出]此成员仅供内部使用的 Outlook，不支持。 
    
 _ulFlags_
  
- [in]若要修改行为的标志：
    
- HSF_LOCAL
    
  - [in]整个项目位于相同的本地存储用作的标头项。
    
- HSF_COPYDESTRUCTIVE
    
  -  [in]优化内部复制操作。 这可能会导致数据丢失。 必须设置**HSF_LOCAL** 。 
    
- HSF_OK
    
  - [in]标头同步成功。 客户端设置从服务器下载信息之后。
    
     _pmsgFull_
    
  - [in]从服务器下载包括邮件头的完整的邮件项目。 请参阅 mapidefs.h **LPMESSAGE**的类型定义。 
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[MAPI 常量](mapi-constants.md)
  
[FEID](feid.md)

