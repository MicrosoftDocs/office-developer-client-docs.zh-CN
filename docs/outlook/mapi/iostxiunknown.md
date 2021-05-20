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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431993"
---
# <a name="iostx--iunknown"></a>IOSTX : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供同步方法。 此接口检索将本地更改复制到服务器和服务器更改到本地存储的必要信息。
  
|||
|:-----|:-----|
|提供者：  <br/> |[IPSTX::GetSyncObject](iostx-setsyncresult.md) <br/> |
|接口标识符：  <br/> |IID_IOSTX  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetLastError](iostx-getlasterror.md) <br/> |获取有关最后一个错误的扩展信息。  <br/> |
|[InitSync](iostx-initsync.md) <br/> |通知本地存储即将启动同步。  <br/> |
|[SyncBeg](iostx-syncbeg.md) <br/> |准备本地存储以用于特定状态同步，并检索要复制的必要信息。  <br/> |
|[SyncEnd](iostx-syncend.md) <br/> |在当前状态中结束同步并退出该状态。  <br/> |
|[SyncHdrBeg](iostx-synchdrbeg.md) <br/> |启动邮件头的同步。  <br/> |
|[SyncHdrEnd](iostx-synchdrend.md) <br/> |结束邮件头的同步。  <br/> |
|[SetSyncResult](iostx-setsyncresult.md) <br/> |设置同步的结果。  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
   
## <a name="remarks"></a>备注

当客户端上载或同步本地存储上的文件夹和文件夹内容时，它会将本地存储从一个状态移动到另一个状态，如关于复制状态机 的状态转换 [图中所示](about-the-replication-state-machine.md)。 以下是客户端将本地存储从一个状态移动到另一个状态的事件顺序：
  
1. 客户端调用 **IOSTX：：InitSync** 以通知本地存储即将开始复制。 
    
2. 根据复制方向和要复制的对象，客户端会调用 **IOSTX：：SyncBeg** 以在适当的状态开始复制。 Outlook向客户端提供必要信息，并且客户端执行复制。 
    
3. 客户端调用 **IOSTX：：SetSyncResult** 以返回复制结果。 
    
4. 客户端调用 **IOSTX：：SyncEnd** 以结束复制，Outlook复制的必需信息。 
    
特别是，在下载邮件项目时，客户端使用 **IOSTX：：SyncHdrBeg** 和 **IOSTX：：SyncHdrEnd** 在本地存储上使用邮件头更新完整邮件项目： 
  
1. **IOSTX：：SyncHdrBeg** 时，本地存储将转换为下载邮件头状态。 Outlook最初为客户端提供本地存储上的当前邮件头。
    
2. 客户端下载包含邮件头的完整邮件项目。
    
3. Outlook使用完整邮件项目更新本地存储上的项。
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)

