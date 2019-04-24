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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 024583926b5d0be638b33b1b60c5d4c5dc74d05b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315090"
---
# <a name="ipstxemulatespooler"></a>IPSTX::EmulateSpooler

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将本地存储设置为模拟 Outlook 协议管理器以将传出邮件后台处理到服务器。
  
```cpp
HRESULT EmulateSpooler( 
    BOOL fEmulate 
);
```

 _fEmulate_
  
>  实时如果本地存储应模拟后台处理程序, 则将此参数设置为 True;如果不是, 则将其设置为 False。 
    
## <a name="remarks"></a>注解

本地存储调用**IPSTX:: EmulateSpooler**作为 Outlook 协议管理器, 将传出队列中的邮件后台打印到后端服务器 (例如, MSN server 或 AOL server) 进行处理。 在同步期间模拟后台打印程序时, 存储将调用以下两种方法: 
  
1. **[IMsgStore:: GetOutgoingQueue](imsgstore-getoutgoingqueue.md)** 获取存储中的邮件的传出队列。 仅当存储模拟 Outlook 协议管理器时, 此方法才会成功。 
    
2. **[IMsgStore:: SetLockState](imsgstore-setlockstate.md)** 在将邮件发送到服务器之前, 仅保护对传出队列中的邮件的唯一访问权限。 仅当存储模拟 Outlook 协议管理器时, 此方法才会成功。 发送邮件后, store 再次调用此方法以释放对它的唯一访问权限。 
    
> [!NOTE]
> 由于 outlook 2002, outlook 协议管理器将替换 MAPI 后台处理程序, 并负责将传出邮件假脱机到后端服务器。 
  
## <a name="see-also"></a>另请参阅



[IPSTX::GetLastError](ipstx-getlasterror.md)
  
[IPSTX::GetSyncObject](ipstx-getsyncobject.md)

