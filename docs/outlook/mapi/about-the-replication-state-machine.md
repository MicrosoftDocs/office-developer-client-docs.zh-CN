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
  
本主题包含 microsoft outlook 2013 和 microsoft outlook 2010 数据复制的状态计算机的概述。
  
> [!NOTE]
> 必须按照本主题中的说明完全实现复制 API, 以便对其有用或受支持。 复制 API 仅可用于从服务器复制 outlook 2013 或 outlook 2010 更改。 
  
## <a name="iostx-and-the-state-machine"></a>IOSTX 和状态机

客户端调用**[IOSTX:: SyncBeg](iostx-syncbeg.md)**, **[IOSTX:: SyncEnd](iostx-syncend.md)**, **[IOSTX:: SyncHdrBeg](iostx-synchdrbeg.md)**, and **[IOSTX:: SyncHdrEnd](iostx-synchdrend.md)** in sequence, 以在本地存储和服务器之间同步 outlook 2013 或 outlook 2010 文件夹和项目。 实际调用顺序取决于需要复制的数据 (例如, outlook 2013 或 outlook 2010 文件夹的层次结构、outlook 2013 或 outlook 2010 文件夹、邮件项目、日历项等) 以及同步的方向 (无论将本地存储中的上传到服务器, 或从服务器下载到本地存储区)。 下面是典型的呼叫序列: 
  
1. 客户端调用**IOSTX:: SyncBeg**开始进行复制, 同时指定状态标识符和指向相应数据结构的地址的指针。 
    
2. outlook 2013 或 outlook 2010 分配数据结构, 并使用客户端所需的信息初始化数据结构。 
    
3. 客户端执行复制, 更新数据结构以传达给本地存储有关复制的所有必要信息。
    
4. 在执行复制之后, 客户端会调用**[IOSTX:: SetSyncResult](iostx-setsyncresult.md)** 和**IOSTX:: SyncEnd** , 以通知本地存储完成特定复制。 
    
> [!NOTE]
> 客户端始终调用**IOSTX:: SyncEnd**结束客户端已在某个特定状态中开始的复制。 根据客户端需要同步的总体数据, 客户端可以调用**IOSTX:: SyncBeg**和**IOSTX:: SyncEnd**多次的一对调用。 
  
## <a name="state-table"></a>状态表

> [!NOTE]
> 下表列出了复制状态机中的所有有效状态, 以及相应的状态标识符和数据结构。 在 "**数据已复制**" 列中, "items" 一词包括邮件、日历、联系人、便笺、日记和任务项。 将更改从本地存储复制到服务器时, 请使用状态标识符指定 "上传" 和带有 "UP" 前缀的数据结构 (例如, **LR_SYNC_UPLOAD_HIERARCHY**和**[UPHIER](uphier.md)** )。 将更改从服务器复制到本地存储时, 请使用指定 "下载" 的状态标识符和包含 "DN" 前缀的数据结构 (例如, **LR_SYNC_DOWNLOAD_HIERARCHY**和**[DNHIER](dnhier.md)** )。 
  
|||||
|:-----|:-----|:-----|:-----|
|**State** <br/> |**复制的数据** <br/> |**状态标识符** <br/> |**数据结构** <br/> |
|[空闲状态](idle-state.md) <br/> | *None*  <br/> |**LR_SYNC_IDLE** <br/> | *None*  <br/> |
|[同步状态](synchronize-state.md) <br/> |文件夹或项目  <br/> |**LR_SYNC** <br/> |**[同步](sync.md)** <br/> |
|[上传层次结构状态](upload-hierarchy-state.md) <br/> |Folders  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |**[UPHIER](uphier.md)** <br/> |
|[上传文件夹状态](upload-folder-state.md) <br/> |Folder  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**[UPFLD](upfld.md)** <br/> |
|[同步内容状态](synchronize-contents-state.md) <br/> |项目数  <br/> |**LR_SYNC_CONTENTS** <br/> |**[SYNCCONT](synccont.md)** <br/> |
|[上传表状态](upload-table-state.md) <br/> |项目数  <br/> |**LR_SYNC_UPLOAD_TABLE** <br/> |**[UPTBL](uptbl.md)** <br/> |
|[上传邮件状态](upload-message-state.md) <br/> |Item  <br/> |**LR_SYNC_UPLOAD_MESSAGE** <br/> |**[UPMSG](upmsg.md)** <br/> |
|[上载读取状态状态](upload-read-status-state.md) <br/> |项目数  <br/> |**LR_SYNC_UPLOAD_MESSAGE_READ** <br/> |**[UPREAD](upread.md)** <br/> |
|[上传删除状态状态](upload-delete-status-state.md) <br/> |项目数  <br/> |**LR_SYNC_UPLOAD_MESSAGE_DEL** <br/> |**[UPDEL](updel.md)** <br/> |
|[下载层次结构状态](download-hierarchy-state.md) <br/> |Folders  <br/> |**LR_SYNC_DOWNLOAD_HIERARCHY** <br/> |**[DNHIER](dnhier.md)** <br/> |
|[下载表状态](download-table-state.md) <br/> |项目数  <br/> |**LR_SYNC_DOWNLOAD_TABLE** <br/> |**[DNTBL](dntbl.md)** <br/> |
|[下载邮件头状态](download-message-header-state.md) <br/> |邮件头  <br/> |**LR_SYNC_DOWNLOAD_HEADER** <br/> |**[HDRSYNC](hdrsync.md)** <br/> |
   
## <a name="state-transition-diagram"></a>状态转换关系图

下图显示了上载或执行文件夹的完全同步 (下载后再上载) 文件夹或文件夹的内容 (邮件、日历、联系人、便笺、任务或日记项目) 时发生的状态转换。 
  
@ @ @ @ @NEED 在此处插入缺少 @ @ @ @ @ @ 的图稿
  
## <a name="example-uploading-a-folder-hierarchy"></a>示例: 上传文件夹层次结构

 上载文件夹层次结构时, 将发生以下步骤序列: 
  
|||||
|:-----|:-----|:-----|:-----|
|**步骤** <br/> |**操作** <br/> |**State** <br/> |**相关数据结构** <br/> |
|1.  <br/> |客户端启动使用**IOSTX:: SyncBeg**的层次结构上载。  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |**UPHIER** <br/> |
|2.  <br/> |outlook 2013 或 outlook 2010 使用客户端的信息填充**UPHIER** 。 这包括初始化 [out] 参数: *iEnt*设置为 0, 并向层次结构中需要上载的文件夹数*美分*。  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |**UPHIER** <br/> |
|3.  <br/> |客户端执行实际的层次结构上载。 举例来说, 如果*分币*为 10, 则对于10个文件夹中的每个文件夹, 客户端都会调用**IOSTX:: SyncBeg**, 并为上载文件夹指定相应的状态标识符和数据结构。  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**UPFLD** <br/> |
|4.  <br/> |outlook 2013 或 outlook 2010 通过初始化其 [out] 参数 (包括文件夹上载的原因、指向 folder 对象的指针以及文件夹的条目 ID) 来填充**UPFLD** 。  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**UPFLD** <br/> |
|5.  <br/> |客户端上传指定的文件夹。  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**UPFLD** <br/> |
|6.  <br/> |客户端将完成文件夹上传的完成情况通知本地存储: 成功后, 客户端将**UPFLD**中的 [in] 参数*ulFlags*设置为**UPF_OK**, 然后调用**IOSTX:: SetSyncResult (S_OK)** 和**IOSTX:: SyncEnd**. 出现故障时, 客户端不会使用**UPF_OK**标志设置*ulFlags* 。 它调用**IOSTX:: SetSyncResult**, 并传入**HRESULT**值和**IOSTX:: SyncEnd**。  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**UPFLD** <br/> |
|7.  <br/> |如果设置了**UPF_OK** , outlook 2013 或 outlook 2010 将清除上传文件夹的内部请求。 然后, 无论*ulFlags*的状态如何, 它都会清除任何内部簿记信息。 虽然要上载的层次结构中仍有一些文件夹 (*iEnt*仍小于*分币*), 但客户端和 outlook 2013 或 outlook 2010 重复步骤3到7。  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**UPFLD** <br/> |
|8.  <br/> |客户端将已完成的层次结构上载通知本地存储: 成功后, 客户端将**UPHIER**中的 [in] 标志设置为**UPH_OK**, 然后调用**IOSTX:: SetSyncResult (S_OK)** 和**IOSTX:: SyncEnd**。 出现故障时, 客户端不会设置**UPH_OK**标志。 它调用**IOSTX:: SetSyncResult**, 并传入**HRESULT**值和**IOSTX:: SyncEnd**。  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |**UPHIER** <br/> |
|9.  <br/> |如果设置了**UPH_OK** , outlook 2013 或 outlook 2010 将清除用于上载层次结构的内部请求。 然后, 无论*ulFlags*的状态如何, 它都会清除任何内部簿记信息。  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |**UPHIER** <br/> |
   
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[SYNCSTATE](syncstate.md)

