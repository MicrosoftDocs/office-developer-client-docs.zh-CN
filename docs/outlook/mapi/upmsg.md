---
title: UPMSG
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 5fe3956b-819a-3edf-0e49-7a44bcfbabcd
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fa8b84e7baed74bda25ec1b20bd79fb121a838fd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587570"
---
# <a name="upmsg"></a>UPMSG

**适用于**： Outlook 2013 |Outlook 2016 
  
用于[上载邮件状态](upload-message-state.md)期间上载 Outlook 项目的信息。
  
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

## <a name="members"></a>Members

 _ulFlags_
  
> [out] / [输入] 要上载期间确定适当的行为的标志。 
    
  - UPM_ASSOC
    
    - [输出]项目相关联。
    
  - UPM_NEW
    
    - [输出]新项目。 
    
  - UPM_MOV
    
    - [输出]项目已移至此处。
    
  - UPM_MOD_PROPS
    
    - [输出]修改项目属性。
    
  - UPM_HEADER
    
    - [输出]Item 是邮件头。
    
  - UPM_OK
    
    - [in]上载成功。 客户端设置此后上载到服务器的信息。
    
  - UPM_MOVED
    
    - [in]项目已成功移动。
    
  - UPM_COMMIT
    
    - [in]现在提交上载状态。
    
  - UPM_DELETE
    
    - [in]现在将删除项目。
    
  - UPM_SAVE
    
    - [in]将更改保存到项目中。
    
_pmsg_
  
> [输出]打开项目对象。 请参阅 mapidefs.h **LPMESSAGE**的类型定义。 
    
_meid_
  
> [输出]项目的条目 ID。
    
_binReserved1_
  
> [in]此成员仅供内部使用的 Outlook，不支持。 
    
_binReserved2_
  
> [in]此成员仅供内部使用的 Outlook，不支持。 
    
_feid_
  
> [输出]源文件夹，如果项目被移条目 ID。
    
_binChg_
  
> [输出]如果项目被移，更改的目标项，键。 请参阅 mapidefs.h **SBinary**的类型定义。 
    
_binPcl_
  
> [输出]如果项目被移，更改目标项，的列表。 请参阅 mapidefs.h **SBinary**的类型定义。 
    
_skeySrc_
  
> [输出]如果项目被移源该项的源键。
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态计算机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)
- [FEID](feid.md)
- [MEID](meid.md)
- [SKEY](skey.md)

