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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360478"
---
# <a name="upfld"></a>UPFLD

**适用于**：Outlook 2013 | Outlook 2016 
  
[上载文件夹状态](upload-folder-state.md)期间上载文件夹的信息。
  
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
  
>  [输出]/[输入] 标志, 以确定对 uplaod 的相应操作。 
    
  - UPF_NEW
    
    - 排除文件夹是新的。
    
  - UPF_MOD_PARENT
    
    - 排除文件夹已移动。
    
  - UPF_MOD_PROPS
    
    - 排除文件夹属性已被修改。
    
  - UPF_DEL
    
    - 排除文件夹已删除。
    
  - UPF_OK
    
    - 实时上载成功。 客户端将文件夹信息上载到服务器后, 会对此进行设置。
    
_pfld_
  
> 排除要上传的打开的文件夹对象。
    
_feid_
  
> [传出] 文件夹的条目 ID。
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md) 
- [关于复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)

