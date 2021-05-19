---
title: 关于复制状态机
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: cf36c6cb-57b4-7b2b-e23d-e0bc8696de96
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a0644e4bf5c6847d61cc59e203d50f61ad142e84
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416480"
---
# <a name="about-the-replication-state-machine"></a>关于复制状态机

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本主题包含用于数据复制和Microsoft Outlook 2013 Microsoft Outlook 2010状态机的概述。
  
> [!NOTE]
> 复制 API 必须完全按照本主题中的说明实现，才能有用或受支持。 复制 API 仅可用于将 2013 Outlook 2013 或 Outlook 2010 更改复制到服务器和从服务器复制。 
  
## <a name="iostx-and-the-state-machine"></a>IOSTX 和状态机

客户端按顺序调用 IOSTX：：SyncBeg、IOSTX：：SyncEnd、IOSTX：：SyncHdrBeg 和 **[IOSTX：：SyncHdrEnd，](iostx-synchdrend.md)** 以在本地存储与服务器之间同步 Outlook 2013 或 Outlook 2010 文件夹和项目。 **[](iostx-syncbeg.md)** **[](iostx-syncend.md)** **[](iostx-synchdrbeg.md)** 实际的调用顺序取决于需要复制的数据 (例如， Outlook 2013 或 Outlook 2010 文件夹的层次结构、Outlook 2013 或 Outlook 2010 文件夹、邮件项目、日历项目等) 以及同步 (无论是从本地存储上载到服务器还是从服务器下载到本地存储) 。 下面是一个典型的调用序列： 
  
1. 客户端调用 **IOSTX：：SyncBeg** 以开始复制，并指定状态标识符和指向相应数据结构地址的指针。 
    
2. Outlook 2013 或 Outlook 2010 分配数据结构，并初始化包含客户端所需信息的数据结构。 
    
3. 客户端执行复制，更新数据结构以将有关复制的任何必要信息传达给本地存储。
    
4. 执行复制后，客户端调用 **[IOSTX：：SetSyncResult](iostx-setsyncresult.md)** 和 **IOSTX：：SyncEnd** 以通知本地存储特定复制的完成情况。 
    
> [!NOTE]
> 客户端始终调用 **IOSTX：：SyncEnd** 以结束客户端已针对特定状态开始进行复制。 根据客户端需要同步的总体数据，客户端可能会多次调用 **IOSTX：：SyncBeg** 和 **IOSTX：：SyncEnd** 对。 
  
## <a name="state-table"></a>状态表

> [!NOTE]
> 下表列出了复制状态机中所有有效状态，以及相应的状态标识符和数据结构。 在" **数据复制"** 列中，术语"items"包括邮件、日历、联系人、便笺、日记和任务项目。 将更改从本地存储复制到服务器时，请使用指定"UPLOAD"的状态标识符和前缀为"UP"的数据结构 (例如 **，LR_SYNC_UPLOAD_HIERARCHY** **[UPHIER](uphier.md)** ) 。 将更改从服务器复制到本地存储时，请使用指定"DOWNLOAD"的状态标识符和前缀为"DN"的数据结构 (例如 LR_SYNC_DOWNLOAD_HIERARCHY 和 **[DNHIER](dnhier.md)** ) 。  
  
|||||
|:-----|:-----|:-----|:-----|
|**State** <br/> |**数据复制** <br/> |**状态标识符** <br/> |**数据结构** <br/> |
|[空闲状态](idle-state.md) <br/> | *无*  <br/> |**LR_SYNC_IDLE** <br/> | *无*  <br/> |
|[同步状态](synchronize-state.md) <br/> |文件夹或项目  <br/> |**LR_SYNC** <br/> |**[SYNC](sync.md)** <br/> |
|[Upload层次结构状态](upload-hierarchy-state.md) <br/> |Folders  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |**[UPHIER](uphier.md)** <br/> |
|[Upload文件夹状态](upload-folder-state.md) <br/> |文件夹  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**[UPFLD](upfld.md)** <br/> |
|[同步内容状态](synchronize-contents-state.md) <br/> |项目  <br/> |**LR_SYNC_CONTENTS** <br/> |**[SYNCCONT](synccont.md)** <br/> |
|[Upload表状态](upload-table-state.md) <br/> |项目  <br/> |**LR_SYNC_UPLOAD_TABLE** <br/> |**[UPTBL](uptbl.md)** <br/> |
|[Upload邮件状态](upload-message-state.md) <br/> |项目  <br/> |**LR_SYNC_UPLOAD_MESSAGE** <br/> |**[UPMSG](upmsg.md)** <br/> |
|[Upload读取状态](upload-read-status-state.md) <br/> |项目  <br/> |**LR_SYNC_UPLOAD_MESSAGE_READ** <br/> |**[UPREAD](upread.md)** <br/> |
|[Upload删除状态](upload-delete-status-state.md) <br/> |项目  <br/> |**LR_SYNC_UPLOAD_MESSAGE_DEL** <br/> |**[UPDEL](updel.md)** <br/> |
|[下载层次结构状态](download-hierarchy-state.md) <br/> |Folders  <br/> |**LR_SYNC_DOWNLOAD_HIERARCHY** <br/> |**[DNHIER](dnhier.md)** <br/> |
|[下载表状态](download-table-state.md) <br/> |项目  <br/> |**LR_SYNC_DOWNLOAD_TABLE** <br/> |**[DNTBL](dntbl.md)** <br/> |
|[下载邮件头状态](download-message-header-state.md) <br/> |邮件头  <br/> |**LR_SYNC_DOWNLOAD_HEADER** <br/> |**[HDRSYNC](hdrsync.md)** <br/> |
   
## <a name="state-transition-diagram"></a>状态转换图

下图显示了在上载或执行完全同步 (下载时发生的状态转换，然后上载) 的文件夹或文件夹内容 (邮件、日历、联系人、便笺、任务或日记项目) 。 
  
@@@@@NEED此处插入缺少的艺术@@@@@@
  
## <a name="example-uploading-a-folder-hierarchy"></a>示例：上载文件夹层次结构

 上载文件夹层次结构时，将执行以下步骤： 
  
|||||
|:-----|:-----|:-----|:-----|
|**步骤** <br/> |**操作** <br/> |**State** <br/> |**相关数据结构** <br/> |
|1.  <br/> |客户端使用 **IOSTX：：SyncBeg 启动层次结构上载**。  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |**UPHIER** <br/> |
|2.  <br/> |Outlook 2013 或 Outlook 2010 会向 **UPHIER 填充** 客户端的信息。 这包括初始化 [out] 参数  *：iEnt*  设置为 0，cEnt  *设置为*  层次结构中需要上载的文件夹数。  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |**UPHIER** <br/> |
|3.  <br/> |客户端执行实际的层次结构上载。 例如，如果  *cEnt*  为 10，则对于这 10 个文件夹，客户端将调用 **IOSTX：：SyncBeg，** 以指定用于上载文件夹的适当状态标识符和数据结构。  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**UPFLD** <br/> |
|4.  <br/> |Outlook 2013 或 Outlook 2010 通过初始化 UPFLD 的 [out] 参数填充 **UPFLD，** 包括文件夹上载的原因、指向文件夹对象的指针以及文件夹的条目 ID。  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**UPFLD** <br/> |
|5.  <br/> |客户端上载指定的文件夹。  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**UPFLD** <br/> |
|6.  <br/> |客户端将文件夹上载完成情况通知本地存储：成功后，客户端使用 **UPF_OK** 在 **UPFLD** 中设置 [in] 参数 *ulFlags，* 然后调用 **IOSTX：：SetSyncResult (S_OK)** 和 **IOSTX：：SyncEnd**。 失败时，客户端不会使用 *"ulFlags"UPF_OK* 标记 **。** 它调用 **IOSTX：：SetSyncResult**，从而传递 **HRESULT** 值和 **IOSTX：：SyncEnd**。  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**UPFLD** <br/> |
|7.  <br/> |如果 **UPF_OK，Outlook** 2013 或 Outlook 2010 将清除上载文件夹的内部请求。 然后，无论  *ulFlags*  的状态如何，它都将清理所有内部记帐信息。 尽管层次结构中仍有文件夹要上载 (*iEnt* 仍小于 *cEnt*) ，但客户端和 Outlook 2013 或 Outlook 2010 重复步骤 3 至 7。  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**UPFLD** <br/> |
|8.  <br/> |客户端将层次结构上载完成通知本地存储：成功后，客户端使用 **UPH_OK** 在 **UPHIER** 中设置 [in] 标志，然后调用 **IOSTX：：SetSyncResult (S_OK)** 和 **IOSTX：：SyncEnd**。 失败时，客户端不会设置 **UPH_OK标志。** 它调用 **IOSTX：：SetSyncResult**，从而传递 **HRESULT** 值和 **IOSTX：：SyncEnd**。  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |**UPHIER** <br/> |
|9.  <br/> |如果 **UPH_OK，Outlook** 2013 或 Outlook 2010 将清除上载层次结构的内部请求。 然后，无论  *ulFlags*  的状态如何，它都将清理所有内部记帐信息。  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |**UPHIER** <br/> |
   
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[SYNCSTATE](syncstate.md)

