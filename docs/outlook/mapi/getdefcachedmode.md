---
title: GetDefCachedMode
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 325b6b47-b6a6-503e-e9bb-65ef7b73d659
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 91a56acf4afc7453496fa89becd905184101c910
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591392"
---
# <a name="getdefcachedmode"></a>GetDefCachedMode

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指示是否启用了专用的 Exchange 存储的缓存 Exchange 模式，并且这是否按策略强制实施。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出：  <br/> |msmapi32.dll  <br/> |
|调用：  <br/> |客户端  <br/> |
|通过实现：  <br/> |Outlook  <br/> |
   
```cpp
BOOL GetDefCachedMode(BOOL *pfPolicy); 

```

## <a name="parameters"></a>参数

 _pfPolicy_
  
> [输出]如果为**true**如果它不返回值强制实施策略， **false** 。 
    
## <a name="return-values"></a>返回值

 **true**
  
- 启用缓存。
    
 **false**
  
- 禁用缓存。
    
## <a name="see-also"></a>另请参阅



[GetDefCachedModeDownloadPubFoldFavs](getdefcachedmodedownloadpubfoldfavs.md)

