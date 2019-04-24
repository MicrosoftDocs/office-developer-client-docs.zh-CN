---
title: PidTagIpmTaskEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmTaskEntryId
api_type:
- HeaderDef
ms.assetid: ec8b7486-b547-4a4e-96e5-1fc825b23f3d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c3845c745dcd2c18525f147308233b94fbce70d4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327840"
---
# <a name="pidtagipmtaskentryid-canonical-property"></a>PidTagIpmTaskEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 Outlook "任务" 文件夹的**条目**id。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_IPM_TASK_ENTRYID  <br/> |
|标识符:  <br/> |0x36D4  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Folder  <br/> |
   
## <a name="remarks"></a>注解

使用 property 和 Stream 对象协议读取或写入该属性。 从收件箱或根文件夹读取和写入该文件。 当存储是主邮件用户的时, 实现必须使用 "收件箱" 文件夹, 并且当存储区是代理人用户的时, 必须使用根文件夹。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)
  
> 指定用于创建和定位邮箱中的特殊文件夹的属性和操作。
    
[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)
  
> 指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历对象代表其他用户操作时与这些对象的交互。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

