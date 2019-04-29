---
title: SKEY
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3f1e8291-6153-c308-94be-ca6745ea86a4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c417e6f4412bc40e8c2ebc056514eb96f60798f0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426805"
---
# <a name="skey"></a>SKEY

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
Outlook 项目的源键。
  
## <a name="quick-info"></a>快速信息

```cpp
struct SKEY 
{ 
    GUID guid; 
    BYTE globcnt[6]; 
};
```

## <a name="members"></a>成员

 _guid_
  
> 创建对象的服务器的 GUID。
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[UPDELE](updele.md)
  
[UPMSG](upmsg.md)
  
[UPREADE](upreade.md)

