---
title: PidLidTaskState 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskState
api_type:
- COM
ms.assetid: 06d1f8a3-53e1-4c9a-9703-75de7a11a772
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 149f238ea53e0669f4d95c8e6c2b17a2b5a1c209
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316532"
---
# <a name="pidlidtaskstate-canonical-property"></a>PidLidTaskState 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示任务的当前分配状态。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskState  <br/> |
|属性集:  <br/> |PSETID_Task  <br/> |
|长 ID (盖子):  <br/> |0x00008113  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>注解

此属性的值必须是下列值之一。
  
|**Value**|**说明**|
|:-----|:-----|
|0x00000000  <br/> |此任务已创建为对应于嵌入在任务拒绝中但未能在本地找到的任务。  <br/> |
|0x00000001  <br/> |未分配任务。  <br/> |
|0x00000002  <br/> |任务是分配的任务的任务受理人的副本。  <br/> |
|0x00000003  <br/> |任务是任务 assigner 的已分配任务的副本。  <br/> |
|0x00000004  <br/> |任务是任务 assigner 的已拒绝任务的副本。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 定义为任务、任务分配和任务更新的电子等效项建模的多个对象。
    
[[毫秒-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)
  
> 指定用于创建和定位邮箱中的特殊文件夹的属性和操作。
    
[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> 在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。
    
[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理客户端与服务器之间的数据传输的顺序和流。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

