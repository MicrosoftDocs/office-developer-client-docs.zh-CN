---
title: SYNC
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3f07fddf-4c42-6ea7-162d-57022166a83f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e856044a1b6345c4e495a75dfb7ca0defa52ceec
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349593"
---
# <a name="sync"></a>SYNC

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
有关在本地存储和服务器之间启动同步的信息。 此信息在[同步状态](synchronize-state.md)期间使用。
  
## <a name="quick-info"></a>快速信息

```cpp
struct SYNC 
{ 
    ULONG ulFlags; 
    LPWSTR pwzPath; 
    FEID Reserved1; 
    MEID Reserved2; 
    LPENTRYLIST pel; 
    ULONG const * pulFolderOptions; 
};
```

## <a name="members"></a>成员

 _ulFlags_
  
- [输出]/[in] 在同步过程中修改行为的以下标志的位掩码:
    
- UPS_UPLOAD_ONLY
    
  - 实时客户端将只执行上载。 Outlook 仅返回本地修改的文件夹。
    
- UPS_DNLOAD_ONLY
    
  - 实时客户端将仅执行下载。 Outlook 不应清除文件夹的上传位。
    
- UPS_THESE_FOLDERS
    
  - 实时客户端将使用提供的条目 id 同步指定的文件夹集。 此标志可以与**UPS_UPLOAD_ONLY**或**UPS_DNLOAD_ONLY**标志组合使用。 
    
- UPS_OK
    
  - 排除同步成功。 在上传或完全同步完成后, 客户端会对此进行设置。
    
- 
    
    > [!NOTE]
    > 即使客户端可以使用复制 API 上传或完全同步 (上载后下载) 文件夹和项目, 客户端也只指定一次复制的一个方向的*ulFlags* (无论是**UPS_UPLOAD_ONLY**还是**UPS_DNLOAD_ONLY**标志。 在完全同步的情况下, 客户端首先使用**UPS_UPLOAD_ONLY**标志执行上载, 然后使用**UPS_DNLOAD_ONLY**标志进行下载。 
  
 _pwzPath_
  
- 排除指向本地存储区的路径。
    
 _Reserved1_
  
- 此成员是为内部使用 Outlook 而保留的, 不受支持。
    
 _Reserved2_
  
- 此成员是为内部使用 Outlook 而保留的, 不受支持。
    
 *pel* 
  
- 实时如果已设置**UPS_THESE_FOLDERS** , 则这是要同步的文件夹的条目 id 列表。 有关**LPENTRYLIST**的类型定义, 请参阅 mapidefs.h。 
    
 _pulFolderOptions_
  
- 实时如果已设置**UPS_THESE_FOLDERS** , 则这是*pel*中对应文件夹的文件夹选项的数组。 [上载文件夹状态](upload-folder-state.md)期间上载*pel*中列出的每个文件夹时, 将使用这些文件夹选项。 有关文件夹选项的详细信息, 请参阅**[UPFLD](upfld.md)**。 
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[MAPI 常量](mapi-constants.md)

