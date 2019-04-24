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
ms.openlocfilehash: 6d7de4d6c14179ddaba4e2ad907f1acc1c53b125
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317176"
---
# <a name="iostx--iunknown"></a>IOSTX : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供同步方法。 此接口检索将本地更改复制到服务器并将服务器更改复制到本地存储的必要信息。
  
|||
|:-----|:-----|
|提供者：  <br/> |[IPSTX::GetSyncObject](iostx-setsyncresult.md) <br/> |
|接口标识符:  <br/> |IID_IOSTX  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetLastError](iostx-getlasterror.md) <br/> |获取有关上一个错误的扩展信息。  <br/> |
|[InitSync](iostx-initsync.md) <br/> |通知本地存储即将启动同步。  <br/> |
|[SyncBeg](iostx-syncbeg.md) <br/> |准备本地存储以在特定状态进行同步并检索要复制的必要信息。  <br/> |
|[SyncEnd](iostx-syncend.md) <br/> |在当前状态结束同步并退出该状态。  <br/> |
|[SyncHdrBeg](iostx-synchdrbeg.md) <br/> |启动邮件头同步。  <br/> |
|[SyncHdrEnd](iostx-synchdrend.md) <br/> |结束邮件头同步。  <br/> |
|[SetSyncResult](iostx-setsyncresult.md) <br/> |设置同步的结果。  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
   
## <a name="remarks"></a>注解

当客户端在本地存储上上载或同步文件夹和文件夹内容时, 它会将本地存储从一个状态移动到另一个状态, 如[关于复制状态机](about-the-replication-state-machine.md)中的状态转换关系图中所示。 以下是客户端将本地存储从一个状态移动到另一个状态的事件的顺序:
  
1. 客户端调用**IOSTX:: InitSync**来通知本地存储即将启动复制。 
    
2. 根据复制方向和要复制的对象, 客户端会调用**IOSTX:: SyncBeg**以在适当的状态下开始复制。 Outlook 向客户端提供必要的信息, 客户端执行复制。 
    
3. 客户端调用**IOSTX:: SetSyncResult**以返回复制的结果。 
    
4. 客户端调用**IOSTX:: SyncEnd**结束复制, 为 Outlook 提供了后续复制所需的信息。 
    
特别是在下载邮件项目时, 客户端使用**IOSTX:: SyncHdrBeg**和**IOSTX:: SyncHdrEnd**更新本地存储区上的邮件头的完整邮件项: 
  
1. 在**IOSTX:: SyncHdrBeg**中, 本地存储将转换为下载邮件标头状态。 Outlook 最初为客户端提供本地存储上的当前邮件头。
    
2. 客户端将完整的邮件项与邮件头一起下载。
    
3. Outlook 使用完整邮件项更新本地存储区上的项目。
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)

