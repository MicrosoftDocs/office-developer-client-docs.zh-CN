---
title: PidLidTaskActualEffort 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskActualEffort
api_type:
- COM
ms.assetid: 8e9a9432-bf50-4333-82ec-fba19dff8006
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7eb51396f4575a8f8f9ce15aff84eb894773e979
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331169"
---
# <a name="pidlidtaskactualeffort-canonical-property"></a>PidLidTaskActualEffort 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示用户执行任务的分钟数。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskActualEffort  <br/> |
|属性集:  <br/> |PSETID_Task  <br/> |
|长 ID (盖子):  <br/> |0x00008110  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>注解

该值必须大于或等于 0, 小于 0x5AE980DF (1525252319), 其中480分钟等于1天, 而2400分钟等于一周 (在一个工作日中为八个小时, 在一个工作周中为五天)。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 指定允许用于联系人和个人通讯组列表对象的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

