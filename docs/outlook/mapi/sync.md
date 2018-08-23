---
title: SYNC
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3f07fddf-4c42-6ea7-162d-57022166a83f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a40046a26efe118e48cdca4749d2e99212bb8bfe
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579838"
---
# <a name="sync"></a>SYNC

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
用于启动本地存储和服务器之间同步的信息。 [同步状态](synchronize-state.md)期间使用此信息。
  
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

## <a name="members"></a>Members

 _ulFlags_
  
- [out] / [in] 同步过程中修改的行为的以下标志位掩码：
    
- UPS_UPLOAD_ONLY
    
  - [in]将仅上载执行客户端。 Outlook 仅返回本地修改的文件夹。
    
- UPS_DNLOAD_ONLY
    
  - [in]将仅下载执行客户端。 Outlook 不应清除上载二进制文件的文件夹。
    
- UPS_THESE_FOLDERS
    
  - [in]客户端将与提供的条目 Id 同步一组指定的文件夹。 可以使用**UPS_UPLOAD_ONLY**或**UPS_DNLOAD_ONLY**标志组合此标志。 
    
- UPS_OK
    
  - [输出]同步已成功。 客户端上载之后设置此或完全同步完成。
    
- 
    
    > [!NOTE]
    > 即使客户端可以上载或完全同步 （上载然后下载） 文件夹和项目复制 API，客户端使用的复制每次只有一个方向指定*ulFlags* — 任一**UPS_UPLOAD_ONLY**或**UPS_DNLOAD_ONLY**标志。 对于完全同步，客户首先进行上载与**UPS_UPLOAD_ONLY**标志，然后用**UPS_DNLOAD_ONLY**标志下载。 
  
 _pwzPath_
  
- [输出]本地存储路径。
    
 _Reserved1_
  
- 此成员仅供内部使用的 Outlook，不支持。
    
 _Reserved2_
  
- 此成员仅供内部使用的 Outlook，不支持。
    
 *pel* 
  
- [in]这是要同步如果**UPS_THESE_FOLDERS**已设置的文件夹的条目 Id 的列表。 请参阅 mapidefs.h **LPENTRYLIST**的类型定义。 
    
 _pulFolderOptions_
  
- [in]如果设置了**UPS_THESE_FOLDERS** ，这是一个数组中*pel*对应的文件夹的文件夹选项。 上载每个[上载文件夹状态](upload-folder-state.md)期间*pel*中列出的文件夹时，将使用这些文件夹选项。 有关文件夹选项的详细信息，请参阅**[UPFLD](upfld.md)**。 
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[MAPI 常量](mapi-constants.md)

