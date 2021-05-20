---
title: UPFLD
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6da9d6b6-a016-ccef-77da-3e037c30450d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c8f7bdc5864c049d8db6f38e92a69c97b6f9dc73
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431356"
---
# <a name="upfld"></a>UPFLD

**适用于**：Outlook 2013 | Outlook 2016 
  
上传文件夹状态期间 [上传文件夹的信息](upload-folder-state.md)。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPFLD 
{ 
    ULONG ulFlags; 
    LPMAPIFOLDER pfld; 
    FEID feid; 
}; 

```

## <a name="members"></a>成员

_ulFlags_
  
>  [out]/[in] 用于确定启动的适当操作的标志。 
    
  - UPF_NEW
    
    - [out]文件夹是新文件夹。
    
  - UPF_MOD_PARENT
    
    - [out]文件夹已移动。
    
  - UPF_MOD_PROPS
    
    - [out]已修改文件夹属性。
    
  - UPF_DEL
    
    - [out]已删除文件夹。
    
  - UPF_OK
    
    - [in]Upload已成功。 客户端在将文件夹信息上载到服务器后进行设置。
    
_pfld_
  
> [out]要上载的打开的文件夹对象。
    
_feid_
  
> [传出] 文件夹的条目 ID。
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md) 
- [关于复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)

