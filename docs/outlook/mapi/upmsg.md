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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427267"
---
# <a name="upmsg"></a>UPMSG

**适用于**：Outlook 2013 | Outlook 2016 
  
上传邮件状态Outlook[上传项目的信息](upload-message-state.md)。
  
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
  
> [out]/[in] 用于确定上传期间适当行为的标志。 
    
  - UPM_ASSOC
    
    - [out]项目已关联。
    
  - UPM_NEW
    
    - [out]新建项目。 
    
  - UPM_MOV
    
    - [out]项目已移动到此处。
    
  - UPM_MOD_PROPS
    
    - [out]已修改项目属性。
    
  - UPM_HEADER
    
    - [out]Item 是邮件头。
    
  - UPM_OK
    
    - [in]Upload已成功。 客户端在将信息上载到服务器后进行设置。
    
  - UPM_MOVED
    
    - [in]项目已成功移动。
    
  - UPM_COMMIT
    
    - [in]现在提交上传状态。
    
  - UPM_DELETE
    
    - [in]立即删除项目。
    
  - UPM_SAVE
    
    - [in]保存对项目的更改。
    
_pmsg_
  
> [out]打开项目对象。 有关 **LPMESSAGE** 的类型定义，请参阅 mapidefs.h。 
    
_meid_
  
> [out]项的条目 ID。
    
_binReserved1_
  
> [in]此成员仅供内部使用，Outlook不支持。 
    
_binReserved2_
  
> [in]此成员仅供内部使用，Outlook不支持。 
    
_feid_
  
> [out]源文件夹的条目 ID（如果项目已移动）。
    
_binChg_
  
> [out]更改目标项的键（如果项目已移动）。 有关 **SBinary** 的类型定义，请参阅 mapidefs.h。 
    
_binPcl_
  
> [out]更改目标项的列表（如果项目已移动）。 有关 **SBinary** 的类型定义，请参阅 mapidefs.h。 
    
_skeySrc_
  
> [out]源项的源键（如果项目已移动）。
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)
- [FEID](feid.md)
- [MEID](meid.md)
- [SKEY](skey.md)

