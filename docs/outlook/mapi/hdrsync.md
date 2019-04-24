---
title: HDRSYNC
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: bf6892d0-a923-e926-5361-59efa49ebdc0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2131197ca24804eec74270100fa70c05c47a27cc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342782"
---
# <a name="hdrsync"></a>HDRSYNC

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
有关在[下载邮件头状态](download-message-header-state.md)期间同步邮件头的信息。
  
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

## <a name="members"></a>成员

 _pupmsg_
  
- 排除本地存储中当前邮件头的信息。
    
 _feidPar_
  
- 排除邮件项目的父文件夹的条目 ID。
    
 _pstmReserved_
  
- [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
 _ulFlags_
  
- 实时修改行为的标志:
    
- HSF_LOCAL
    
  - 实时完整项目位于与标题项目相同的本地存储中。
    
- HSF_COPYDESTRUCTIVE
    
  -  实时优化内部副本操作。 这可能会导致数据丢失。 必须设置**HSF_LOCAL** 。 
    
- HSF_OK
    
  - 实时标头同步成功。 客户端从服务器下载信息之后对此进行设置。
    
     _pmsgFull_
    
  - 实时包含从服务器下载的邮件头的完整邮件项目。 有关**LPMESSAGE**的类型定义, 请参阅 mapidefs.h。 
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[MAPI 常量](mapi-constants.md)
  
[FEID](feid.md)

