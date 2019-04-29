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
ms.openlocfilehash: 8e8a6ac07e14af52337b6e280fa58274df453c65
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412742"
---
# <a name="getdefcachedmode"></a>GetDefCachedMode

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示是否启用专用 exchange 存储的缓存 Exchange 模式, 以及是否通过策略强制实施。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出者:  <br/> |msmapi32  <br/> |
|调用者：  <br/> |Client  <br/> |
|实现者：  <br/> |Outlook  <br/> |
   
```cpp
BOOL GetDefCachedMode(BOOL *pfPolicy); 

```

## <a name="parameters"></a>参数

 _pfPolicy_
  
> 排除如果返回值由策略强制, 则**为 true** ; 如果不是, 则为**false** 。 
    
## <a name="return-values"></a>返回值

 **true**
  
- 启用缓存。
    
 **该值**
  
- 缓存被禁用。
    
## <a name="see-also"></a>另请参阅



[GetDefCachedModeDownloadPubFoldFavs](getdefcachedmodedownloadpubfoldfavs.md)

