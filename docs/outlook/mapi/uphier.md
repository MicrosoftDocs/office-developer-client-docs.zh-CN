---
title: UPHIER
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a75ca0dd-9c50-2a9f-6c59-1f8020833a01
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 45ef7ce9291376ac020035f0bde6172caf6cc01b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414919"
---
# <a name="uphier"></a>UPHIER
 
**适用于**：Outlook 2013 | Outlook 2016 
  
在上载层次结构状态期间同步 [文件夹层次结构的信息](upload-hierarchy-state.md)。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPHIER 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved; 
    UINT iEnt; 
    UINT cEnt; 
};
```

## <a name="members"></a>成员

_ulFlags_
  
> [in]用于修改同步文件夹层次结构时的行为的标志。
    
  - UPH_OK
    
    - [in]Upload已成功。 客户端在将信息成功上载到服务器后进行设置。 看到此标志后，Outlook清除指示文件夹层次结构需要更新的任何内部记帐信息。 
    
    - 如果上传未成功，客户端将传递 HRESULT。
    
_pstmReserved_
  
> [out]此成员仅供Outlook使用，不受支持。
    
_iEnt_
  
> [out]索引，跟踪同步  *cEnt 指定的文件夹数*  。 
    
_cEnt_
  
> [out]不同步的文件夹数。
    
## <a name="see-also"></a>另请参阅

- [关于复制 API](about-the-replication-api.md)
- [关于复制状态机](about-the-replication-state-machine.md)
- [MAPI 常量](mapi-constants.md)

