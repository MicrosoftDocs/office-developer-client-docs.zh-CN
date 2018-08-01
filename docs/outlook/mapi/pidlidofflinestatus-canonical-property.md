---
title: PidLidOfflineStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidOfflineStatus
api_type:
- COM
ms.assetid: ee69f0c4-b552-4cfd-8a39-a822d414549e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 34f50766c2c45d85bbb0bd9e12d32c5dd87e3cac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776930"
---
# <a name="pidlidofflinestatus-canonical-property"></a>PidLidOfflineStatus 规范属性

  
  
**适用于**： Outlook 
  
确定实现 [MS LISTSWS] 的服务器上的文档文件的状态。
  
|||
|:-----|:-----|
|相关的属性  <br/> |dispidOfflineStatus  <br/> |
|属性进行设置：  <br/> |PSETID_Common  <br/> |
|长 ID （盖）：  <br/> |0x000085B9  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>说明

下表显示了此属性的可能值。
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |未签出文档。  <br/> |
|1  <br/> |文档是当前用户签出。  <br/> |
|2  <br/> |文档未签出，但当前用户具有用于编辑当前计算机上保存的文件的副本。  <br/> |
   
此属性的本地计算并不会发送到服务器随时除非用户将项目拖动到另一个帐户。 在这种情况下，将其视为用户定义的自定义属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]] 
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

