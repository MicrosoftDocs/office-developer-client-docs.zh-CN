---
title: PidLidTaskMode 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskMode
api_type:
- COM
ms.assetid: 185db683-301a-4d91-a583-6959853fa1ad
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bc8e4dfe934d516c07d5532ba6a95e51a3cbf962
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578078"
---
# <a name="pidlidtaskmode-canonical-property"></a>PidLidTaskMode 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指定任务的工作分配状态。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskMode  <br/> |
|属性进行设置：  <br/> |PSETID_Common  <br/> |
|长 ID （盖）：  <br/> |0x00008518  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Task  <br/> |
   
## <a name="remarks"></a>注解

值必须是下列选项之一。
  
|**值**|**说明**|
|:-----|:-----|
|0x00000000  <br/> |未分配的任务。  <br/> |
|0x00000001  <br/> |任务请求中嵌入任务。  <br/> |
|0x00000002  <br/> |任务已接受任务受理人。  <br/> |
|0x00000003  <br/> |任务工作负责人被拒绝任务。  <br/> |
|0x00000004  <br/> |任务更新中嵌入任务。  <br/> |
|0x00000005  <br/> |任务已分配给任务分配人。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 定义模型的任务、 任务分配和任务更新电子等效项的多个对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

