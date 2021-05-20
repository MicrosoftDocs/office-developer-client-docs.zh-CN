---
title: UPTBL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 39d9ad3b-ff4b-8378-a3ac-d5621c7ef7f1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b401f54df020fb6553cbdcc5b85206ee422a8429
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438111"
---
# <a name="uptbl"></a>UPTBL

**适用于**：Outlook 2013 | Outlook 2016 
  
上传表状态期间上传 [文件夹内容的信息](upload-table-state.md)。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPTBL 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved; 
    LPSTR pszName; 
    FEID feid; 
    UINT uintReserved; 
    UPTBLE rgte[2]; 
    UINT iEnt; 
    UINT cEnt; 
    PUPMOV pupmovHead; 
    void* pReserved; 
};
```

## <a name="members"></a>成员

_ulFlags_
  
> [in]用于确定上载过程中的适当行为的标志。
    
  - UPT_OK
    
    - [in]Upload已成功。 客户端在将文件夹内容上载到服务器后进行设置。
    
_pstmReserved_
  
> [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_pszName_
  
> [传出] 文件夹的名称。
    
_feid_
  
> [传出] 文件夹的条目 ID。
    
_uintReserved_
  
> [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。 
    
_rgte_
  
> [out]用于保存文件夹中正常 (或非隐藏) 项目以及关联的 (或隐藏) 项的以下信息的结构  _：rgte[0]_ 用于普通项目  _，rgte[1]_ 用于关联项目。 
    
   - 新项或修改项的数量
   - 读取项目的数量 
   - 已删除项目的数量
    
 _iEnt_
  
> [out]索引，跟踪由 cEnt 指定的更改  _数的上载_。
    
_cEnt_
  
> [out]文件夹的更改数。
    
_pupmovHead_
  
> [out] [UPMOV 结构](upmov.md) 链。 
    
_pReserved_
  
> [传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)
- [UPTBLE](uptble.md)

