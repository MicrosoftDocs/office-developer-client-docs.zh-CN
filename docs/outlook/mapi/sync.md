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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433806"
---
# <a name="sync"></a>SYNC

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在本地存储与服务器之间启动同步的信息。 此信息在同步状态 [期间使用](synchronize-state.md)。
  
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
  
- [out]/[in] 在同步期间修改行为的以下标志的位掩码：
    
- UPS_UPLOAD_ONLY
    
  - [in]客户端将仅执行上载。 Outlook返回本地修改的文件夹。
    
- UPS_DNLOAD_ONLY
    
  - [in]客户端将仅执行下载。 Outlook无法清除文件夹的上载位。
    
- UPS_THESE_FOLDERS
    
  - [in]客户端将同步指定的文件夹集与提供的条目 ID。 此标志可以与 UPS_UPLOAD_ONLY **或****UPS_DNLOAD_ONLY** 标志结合使用。 
    
- UPS_OK
    
  - [out]同步成功。 客户端在上载或完全同步完成后进行设置。
    
- 
    
    > [!NOTE]
    > 即使客户端可以上载或完全同步 (上载，然后使用复制 API 下载) 文件夹和项目，但客户端一次仅指定一个方向的  *ulFlags（* **UPS_UPLOAD_ONLY** 或 **UPS_DNLOAD_ONLY** 标记）。 在完全同步的情况下，客户端首先执行具有 UPS_UPLOAD_ONLY 标志的上载， **然后** 执行具有 UPS_DNLOAD_ONLY **标记的** 下载。 
  
 _pwzPath_
  
- [out]本地存储的路径。
    
 _Reserved1_
  
- 此成员仅供内部使用，Outlook不支持。
    
 _Reserved2_
  
- 此成员仅供内部使用，Outlook不支持。
    
 *pel* 
  
- [in]这是要同步的文件夹的条目 **UPS_THESE_FOLDERS已设置** 。 有关 **LPENTRYLIST** 的类型定义，请参阅 mapidefs.h。 
    
 _将folderOptions_
  
- [in]这是  *pel*  中相应文件夹的文件夹选项数组（ **如果UPS_THESE_FOLDERS** 已设置）。 在上传文件夹状态期间上传  *pel*  中列出的每个文件夹时，会使用这些 [文件夹选项](upload-folder-state.md)。 有关文件夹选项的详细信息，请参阅 **[UPFLD](upfld.md)**。 
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[MAPI 常量](mapi-constants.md)

