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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438951"
---
# <a name="ipstxemulatespooler"></a>IPSTX::EmulateSpooler

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置本地存储以模拟 Outlook 协议管理器，以将传出邮件后台打印到服务器。
  
```cpp
HRESULT EmulateSpooler( 
    BOOL fEmulate 
);
```

 _fEmulate_
  
>  [in]如果本地存储应模拟后台处理程序，将此参数设置为 True;如果没有，设置为 False。 
    
## <a name="remarks"></a>备注

本地存储调用 **IPSTX：：EmulateSpooler** 充当 Outlook 协议管理器，将传出队列中的邮件后台打印到后端服务器 (例如，MSN 服务器或 AOL 服务器) 进行处理。 在同步期间模拟后台处理程序，存储随后将调用以下两种方法： 
  
1. **[IMsgStore：：GetOutgoingQueue](imsgstore-getoutgoingqueue.md)** 获取存储中邮件的传出队列。 只有当存储正在模拟协议管理器时，此方法Outlook成功。 
    
2. **[IMsgStore：：SetLockState，](imsgstore-setlockstate.md)** 以确保在将邮件发送到服务器之前，唯一访问传出队列中的邮件。 只有当存储正在模拟协议管理器时，此方法Outlook成功。 发送邮件后，存储会再次调用此方法以释放对它的唯一访问权限。 
    
> [!NOTE]
> 自 2002 Outlook以来，Outlook 协议管理器取代了 MAPI 后台处理程序，并负责将传出邮件后台打印到后端服务器。 
  
## <a name="see-also"></a>另请参阅



[IPSTX::GetLastError](ipstx-getlasterror.md)
  
[IPSTX::GetSyncObject](ipstx-getsyncobject.md)

