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
ms.openlocfilehash: 537b45420390903d67722c074a1edcc04a0aede8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418832"
---
# <a name="pidlidofflinestatus-canonical-property"></a>PidLidOfflineStatus 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
确定在实现 [LISTSWS] 的服务器上的文档文件的状态。
  
|||
|:-----|:-----|
|关联属性  <br/> |dispidOfflineStatus  <br/> |
|属性集:  <br/> |PSETID_Common  <br/> |
|长 ID (盖子):  <br/> |0x000085B9  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规邮件  <br/> |
   
## <a name="remarks"></a>说明

下表显示了此属性的可能值。
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |文档未签出。  <br/> |
|1  <br/> |将文档签出给当前用户。  <br/> |
|双面  <br/> |文档未签出, 但当前用户具有保存为在当前计算机上进行编辑的文件的副本。  <br/> |
   
此属性在本地计算且不会在任何时间发送到服务器, 除非用户将项目拖动到另一个帐户。 在这种情况下, 它将被视为用户定义的自定义属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]] 
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

