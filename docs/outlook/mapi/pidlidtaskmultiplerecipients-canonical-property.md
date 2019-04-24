---
title: PidLidTaskMultipleRecipients 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskMultipleRecipients
api_type:
- COM
ms.assetid: 28ba9997-72dd-465f-94a7-35a317a361ef
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3b260917e107086dee6176f73b6c82c3a1825327
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360065"
---
# <a name="pidlidtaskmultiplerecipients-canonical-property"></a>PidLidTaskMultipleRecipients 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供有关任务收件人的优化提示。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskMultRecips  <br/> |
|属性集:  <br/> |PSETID_Task  <br/> |
|长 ID (盖子):  <br/> |0x00008120  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>注解

如果设置此属性, 则必须将此属性设置为零个或多个下列值的按位**或**运算。 
  
|**Name**|**Value**|**说明**|
|:-----|:-----|:-----|
|发件箱  <br/> |0x00000001  <br/> |任务包含多个主要收件人。  <br/> |
|接收时间  <br/> |0x00000002  <br/> |尽管发送的提示不存在, 但客户端检测到该任务有多个主收件人。  <br/> |
|Reserved  <br/> |0x00000004  <br/> |此值为保留值。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 定义为任务、任务分配和任务更新的电子等效项建模的多个对象。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

