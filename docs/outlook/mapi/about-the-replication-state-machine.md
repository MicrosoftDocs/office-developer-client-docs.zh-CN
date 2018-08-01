---
title: 关于复制状态计算机
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: cf36c6cb-57b4-7b2b-e23d-e0bc8696de96
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9ea18f8e5c7eb758780727829fb1e18d2a19ec92
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774480"
---
# <a name="about-the-replication-state-machine"></a>关于复制状态计算机

  
  
**适用于**： Outlook 
  
本主题包含 Microsoft Outlook 2013 和 Microsoft Outlook 2010 的数据复制的状态机器的概述。
  
> [!NOTE]
> 复制 API 必须完全实现根据本主题中才能成为有用或受支持的说明。 以独占方式可以与服务器复制 Outlook 2013 或 Outlook 2010 的更改复制 API。 
  
## <a name="iostx-and-the-state-machine"></a>IOSTX 和状态机

客户端调用**[IOSTX::SyncBeg](iostx-syncbeg.md)**、 **[IOSTX::SyncEnd](iostx-syncend.md)**、 **[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)** 和**[IOSTX::SyncHdrEnd](iostx-synchdrend.md)** 同步 Outlook 2013 或 Outlook 2010 中的文件夹和项目的本地存储区和服务器之间的顺序。 实际的调用序列取决于需要 （对于示例、 Outlook 2013 或 Outlook 2010 中的文件夹层次结构、 Outlook 2013 或 Outlook 2010 文件夹、 邮件项目、 日历项和等等） 复制的数据，并同步 （是否将方向从本地存储上载到服务器，或从服务器下载到本地存储）。 下面是典型调用序列： 
  
1. 客户端调用**IOSTX::SyncBeg**开始复制指定的状态标识符和一个指向相应的数据结构的地址。 
    
2. Outlook 2013 或 Outlook 2010 分配的数据结构，并初始化与客户端所需的信息的数据结构。 
    
3. 客户端执行复制，更新要将复制的任何所需信息传达给本地存储的数据结构。
    
4. 执行复制之后, 客户端调用**[IOSTX::SetSyncResult](iostx-setsyncresult.md)** 和**IOSTX::SyncEnd**通知本地存储的特定的复制完成。 
    
> [!NOTE]
> 客户端始终调用**IOSTX::SyncEnd**结束客户端的特定状态已开始复制。 根据客户端需要同步的总体数据，客户端可以多次调用**IOSTX::SyncBeg**和**IOSTX::SyncEnd**呼叫的对。 
  
## <a name="state-table"></a>状态表

> [!NOTE]
> 下表列出了在复制状态机，以及相应的状态标识符和数据结构中的所有有效状态。 在**数据复制**列中，术语"项目"包含邮件、 日历、 联系人、 注释、 日志，和任务项目。 时将从本地存储的更改复制到服务器，使用"向上"前缀 （例如， **LR_SYNC_UPLOAD_HIERARCHY**和**[UPHIER](uphier.md)** ） 指定"上载"的状态标识符和数据结构。 当从服务器的更改复制到本地存储区中，使用"DN"前缀 （例如， **LR_SYNC_DOWNLOAD_HIERARCHY**和**[DNHIER](dnhier.md)** ） 指定"下载"的状态标识符和数据结构。 
  
|||||
|:-----|:-----|:-----|:-----|
|**State** <br/> |**复制数据** <br/> |**状态标识符** <br/> |**数据结构** <br/> |
|[空闲状态](idle-state.md) <br/> | *None*  <br/> |**LR_SYNC_IDLE** <br/> | *None*  <br/> |
|[同步状态](synchronize-state.md) <br/> |文件夹或项目  <br/> |**LR_SYNC** <br/> |**[SYNC](sync.md)** <br/> |
|[上载层次结构状态](upload-hierarchy-state.md) <br/> |文件夹  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |**[UPHIER](uphier.md)** <br/> |
|[上载文件夹状态](upload-folder-state.md) <br/> |Folder  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**[UPFLD](upfld.md)** <br/> |
|[同步内容状态](synchronize-contents-state.md) <br/> |Items  <br/> |**LR_SYNC_CONTENTS** <br/> |**[SYNCCONT](synccont.md)** <br/> |
|[上载表状态](upload-table-state.md) <br/> |Items  <br/> |**LR_SYNC_UPLOAD_TABLE** <br/> |**[UPTBL](uptbl.md)** <br/> |
|[上载邮件状态](upload-message-state.md) <br/> |Item  <br/> |**LR_SYNC_UPLOAD_MESSAGE** <br/> |**[UPMSG](upmsg.md)** <br/> |
|[上载读取状态状态](upload-read-status-state.md) <br/> |Items  <br/> |**LR_SYNC_UPLOAD_MESSAGE_READ** <br/> |**[UPREAD](upread.md)** <br/> |
|[上载删除状态状态](upload-delete-status-state.md) <br/> |Items  <br/> |**LR_SYNC_UPLOAD_MESSAGE_DEL** <br/> |**[UPDEL](updel.md)** <br/> |
|[下载层次结构状态](download-hierarchy-state.md) <br/> |文件夹  <br/> |**LR_SYNC_DOWNLOAD_HIERARCHY** <br/> |**[DNHIER](dnhier.md)** <br/> |
|[下载表状态](download-table-state.md) <br/> |Items  <br/> |**LR_SYNC_DOWNLOAD_TABLE** <br/> |**[DNTBL](dntbl.md)** <br/> |
|[下载邮件头状态](download-message-header-state.md) <br/> |邮件头  <br/> |**LR_SYNC_DOWNLOAD_HEADER** <br/> |**[HDRSYNC](hdrsync.md)** <br/> |
   
## <a name="state-transition-diagram"></a>状态转换关系图

下图显示上载或的文件夹或文件夹 （邮件、 日历、 联系人、 注释、 任务或日记项目） 的内容执行完全同步 （下载上载后跟） 时发生的状态转换。 
  
插入图片此处缺少到 @@@NEED。
  
## <a name="example-uploading-a-folder-hierarchy"></a>示例： 上载文件夹层次结构

 当上载文件夹层次结构，下面的步骤顺序发生： 
  
|||||
|:-----|:-----|:-----|:-----|
|**步骤** <br/> |**操作** <br/> |**State** <br/> |**相关的数据结构** <br/> |
|1。  <br/> |客户端启动与**IOSTX::SyncBeg**层次结构上载。  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |**UPHIER** <br/> |
|2。  <br/> |Outlook 2013 或 Outlook 2010 填充**UPHIER**与客户端的信息。 这包括初始化 [out] 的参数： *iEnt*设置为 0 度和 *%* 到需要上载层次结构中的文件夹的数目。  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |**UPHIER** <br/> |
|3.  <br/> |客户端执行的实际层次结构上载。 例如，如果 *%* 为 10，为每个 10 的文件夹中，客户端调用**IOSTX::SyncBeg**，指定相应的状态标识符和数据结构，用于上载一个文件夹。  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**UPFLD** <br/> |
|4。  <br/> |Outlook 2013 或 Outlook 2010 填充**UPFLD**初始化其 [out] 的参数，包括文件夹上载，该指针指向 folder 对象，其原因和文件夹的条目 ID。  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**UPFLD** <br/> |
|5。  <br/> |客户端上载指定的文件夹。  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**UPFLD** <br/> |
|6。  <br/> |客户端通知的本地文件夹上载完成存储： 一旦成功，客户端设置 [in] 参数*ulFlags* **UPFLD**与**UPF_OK**，然后调用**IOSTX::SetSyncResult (S_OK)** 和**IOSTX::SyncEnd 中**. 遇到故障，客户端未设置*ulFlags*与**UPF_OK**标志。 它调用**IOSTX::SetSyncResult**，传递的**HRESULT**值和**IOSTX::SyncEnd**中。  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**UPFLD** <br/> |
|7。  <br/> |如果设置**UPF_OK** ，Outlook 2013 或 Outlook 2010 将清除上载文件夹的内部请求。 然后*ulFlags*的状态，无论它将清除任何内部记帐信息。 要上载的层次结构中还有文件夹时 （*iEnt*是仍小于 *%*），在客户端和 Outlook 2013 或 Outlook 2010 重复步骤 3 至 7。  <br/> |**LR_SYNC_UPLOAD_FOLDER** <br/> |**UPFLD** <br/> |
|8。  <br/> |客户端通知的层次结构上载完成的本地存储： 一旦成功，客户端设置 [in] **IOSTX::SetSyncResult (S_OK)** 和**IOSTX::SyncEnd**中与**UPH_OK**，然后调用**UPHIER**标记。 遇到故障，客户端不会设置**UPH_OK**标志。 它调用**IOSTX::SetSyncResult**，传递的**HRESULT**值和**IOSTX::SyncEnd**中。  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |**UPHIER** <br/> |
|9。  <br/> |如果设置**UPH_OK** ，Outlook 2013 或 Outlook 2010 将清除上载层次结构的内部请求。 然后*ulFlags*的状态，无论它将清除任何内部记帐信息。  <br/> |**LR_SYNC_UPLOAD_HIERARCHY** <br/> |**UPHIER** <br/> |
   
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[SYNCSTATE](syncstate.md)

