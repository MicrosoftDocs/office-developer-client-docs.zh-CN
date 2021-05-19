---
title: GetDefCachedModeDownloadPubFoldFavs
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2dd95561-ed8f-8a3b-6532-b53556f16666
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5e623c9d40ffd2dd276bd9601676244644bb3402
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417705"
---
# <a name="getdefcachedmodedownloadpubfoldfavs"></a>GetDefCachedModeDownloadPubFoldFavs

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示是否启用公用文件夹收藏夹文件夹的缓存Exchange 模式，以及这是否由策略强制执行。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出者：  <br/> |msmapi32.dll  <br/> |
|调用者：  <br/> |客户端  <br/> |
|实现者：  <br/> |Outlook  <br/> |
   
```cpp
BOOL GetDefCachedModeDownloadPubFoldFavs(BOOL *pfPolicy); 

```

## <a name="parameters"></a>参数

 _pfPolicy_
  
> [out]如果返回值是由策略强制执行的，则返回值为 **true;** 如果返回值不是，则返回 **false。** 
    
## <a name="return-values"></a>返回值

 **true**
  
- 缓存已启用。
    
 **false**
  
- 缓存已禁用。
    
## <a name="see-also"></a>另请参阅



[GetDefCachedMode](getdefcachedmode.md)

