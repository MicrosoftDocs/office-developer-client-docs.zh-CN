---
title: UPMSG
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 5fe3956b-819a-3edf-0e49-7a44bcfbabcd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1e0e2f9b794c4cee25488a754290922e58b7658d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338869"
---
# <a name="upmsg"></a>UPMSG

**适用于**：Outlook 2013 | Outlook 2016 
  
[上载邮件状态](upload-message-state.md)期间上载 Outlook 项目的信息。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPMSG 
{ 
    ULONG ulFlags; 
    LPMESSAGE pmsg; 
    MEID meid; 
    SBinary binReserved1; 
    SBinary binReserved2; 
    FEID feid; 
    SBinary binChg; 
    SBinary binPcl; 
    SKEY skeySrc; 
};
```

## <a name="members"></a>成员

 _ulFlags_
  
> [输出]/[in] 标志以确定上载过程中的相应行为。 
    
  - UPM_ASSOC
    
    - 排除项目相关联。
    
  - UPM_NEW
    
    - 排除新项目。 
    
  - UPM_MOV
    
    - 排除项目已移至此处。
    
  - UPM_MOD_PROPS
    
    - 排除修改了项目属性。
    
  - UPM_HEADER
    
    - 排除Item 为邮件头。
    
  - UPM_OK
    
    - 实时上载成功。 客户端将信息上载到服务器后对此进行设置。
    
  - UPM_MOVED
    
    - 实时已成功移动项目。
    
  - UPM_COMMIT
    
    - 实时立即提交上载状态。
    
  - UPM_DELETE
    
    - 实时立即删除项目。
    
  - UPM_SAVE
    
    - 实时保存对项目所做的更改。
    
_pmsg_
  
> 排除打开项目对象。 有关**LPMESSAGE**的类型定义, 请参阅 mapidefs.h。 
    
_meid_
  
> 排除项目的条目 ID。
    
_binReserved1_
  
> 实时此成员是为内部使用 Outlook 而保留的, 不受支持。 
    
_binReserved2_
  
> 实时此成员是为内部使用 Outlook 而保留的, 不受支持。 
    
_feid_
  
> 排除源文件夹的条目 ID (如果已移动项目)。
    
_binChg_
  
> 排除如果已移动项, 则更改目标项的键。 有关**SBinary**的类型定义, 请参阅 mapidefs.h。 
    
_binPcl_
  
> 排除如果项目已移动, 则更改目标项的列表。 有关**SBinary**的类型定义, 请参阅 mapidefs.h。 
    
_skeySrc_
  
> 排除源项的源项 (如果已移动项)。
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)
- [FEID](feid.md)
- [MEID](meid.md)
- [SKEY](skey.md)

