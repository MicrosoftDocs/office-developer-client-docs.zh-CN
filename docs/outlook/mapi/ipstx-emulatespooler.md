---
title: IPSTXEmulateSpooler
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTX.EmulateSpooler
api_type:
- COM
ms.assetid: aec72e51-1f75-b2c5-76ca-626cd21fbc7d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a8e353bbb4f276169ae26ba9d05821158bf55f00
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776063"
---
# <a name="ipstxemulatespooler"></a>IPSTX::EmulateSpooler

  
  
**适用于**： Outlook 
  
设置要模拟 Outlook 协议管理器后台打印到的服务器的传出邮件的本地存储。
  
```cpp
HRESULT EmulateSpooler( 
    BOOL fEmulate 
);
```

 _fEmulate_
  
>  [in]将此参数设置为 True，如果本地存储应模拟后台处理程序;将其设置为 false，则如果不需要。 
    
## <a name="remarks"></a>说明

本地存储调用**IPSTX::EmulateSpooler**操作作为 Outlook 协议管理器中，为后端服务器 （例如，MSN 服务器或 AOL 服务器） 进行处理传出队列中的后台打印邮件。 存储同步过程中模拟后台处理程序，然后调用这两种方法： 
  
1. **[IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md)** ，以获取存储中的传出消息的队列。 此方法成功，仅当存储在模拟 Outlook 协议管理器。 
    
2. **[IMsgStore::SetLockState](imsgstore-setlockstate.md)** 保护之前将其发送到服务器的唯一的访问权传出队列中的邮件。 此方法成功，仅当存储在模拟 Outlook 协议管理器。 发送消息后, 存储调用此方法再次来释放唯一访问它。 
    
> [!NOTE]
> Outlook 2002 相 Outlook 协议经理替换 MAPI 后台处理程序和变为负责对后端服务器进行后台打印传出邮件。 
  
## <a name="see-also"></a>另请参阅



[IPSTX::GetLastError](ipstx-getlasterror.md)
  
[IPSTX::GetSyncObject](ipstx-getsyncobject.md)

