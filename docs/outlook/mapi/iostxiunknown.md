---
title: IOSTX IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX
api_type:
- COM
ms.assetid: f374d8d9-be8e-2489-d5fe-8a92e0ecfc6f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7419a0df7a2f3b76caeeb1ca564624d437eddd52
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775981"
---
# <a name="iostx--iunknown"></a>IOSTX : IUnknown

  
  
**适用于**： Outlook 
  
提供同步的方法。 此接口检索将本地更改复制到的服务器和服务器到本地存储的更改的必要信息。
  
|||
|:-----|:-----|
|提供者：  <br/> |[IPSTX::GetSyncObject](iostx-setsyncresult.md) <br/> |
|接口标识符：  <br/> |IID_IOSTX  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[时出错](iostx-getlasterror.md) <br/> |获取有关扩展的信息的最后一个错误。  <br/> |
|[InitSync](iostx-initsync.md) <br/> |通知的本地存储同步即将开始。  <br/> |
|[SyncBeg](iostx-syncbeg.md) <br/> |为特定状态同步准备本地存储并检索复制的必需信息。  <br/> |
|[SyncEnd](iostx-syncend.md) <br/> |结束同步中的当前状态并退出该状态。  <br/> |
|[SyncHdrBeg](iostx-synchdrbeg.md) <br/> |邮件头的启动同步。  <br/> |
|[SyncHdrEnd](iostx-synchdrend.md) <br/> |邮件头的两端同步。  <br/> |
|[SetSyncResult](iostx-setsyncresult.md) <br/> |设置同步的结果。  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
   
## <a name="remarks"></a>说明

当客户端上载或同步文件夹和本地存储区上的文件夹内容时，将本地存储从一种状态到另一个[有关复制状态机](about-the-replication-state-machine.md)中的状态转换关系图中所示。 以下是从一种状态的本地存储移动到另一个客户端的事件的顺序：
  
1. 客户端调用**IOSTX::InitSync** ，告知复制即将开始的本地存储。 
    
2. 复制和要复制的对象的方向，根据客户端调用**IOSTX::SyncBeg**开始复制中相应的状态。 Outlook 提供了客户端所需的信息，并在客户端执行复制。 
    
3. 客户端调用**IOSTX::SetSyncResult**返回复制的结果。 
    
4. 客户端调用**IOSTX::SyncEnd**结束复制，提供 Outlook 后续复制所需的信息。 
    
具体而言，当下载邮件项目，客户端使用**IOSTX::SyncHdrBeg**和**IOSTX::SyncHdrEnd**更新完整的邮件项目上本地存储消息标头： 
  
1. 时**IOSTX::SyncHdrBeg**，本地存储转换到该下载邮件头状态。 Outlook 最初上本地存储为客户提供当前的邮件头。
    
2. 客户端下载完整邮件项目以及邮件头。
    
3. Outlook 更新完整的邮件项目上本地存储的项。
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)

