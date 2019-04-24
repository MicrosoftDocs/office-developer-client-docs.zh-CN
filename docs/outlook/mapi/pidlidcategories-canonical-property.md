---
title: PidLidCategories 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidCategories
api_type:
- COM
ms.assetid: 6ad2aedc-405b-475e-ac76-7ecbbef28f73
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b2047f04f3f4a8d2b3e58e07a71e7e2463eff9cf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344973"
---
# <a name="pidlidcategories-canonical-property"></a>PidLidCategories 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定项的类别列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidCategories  <br/> |
|属性集:  <br/> |PS_PUBLIC_STRINGS  <br/> |
|长 ID (盖子):  <br/> |0x00002328  <br/> |
|数据类型：  <br/> |PT_MV_UNICODE  <br/> |
|区域：  <br/> |常见  <br/> |
   
## <a name="remarks"></a>注解

若要生成关键字标头字段, 客户端必须将此属性的值设置为所需的值。 此属性包含多个字符串;应将每个类别映射到单个关键字。
  
多用途 Internet 邮件扩展 (MIME) 编写器应将此属性的每个子值复制到关键字标头字段中的单独关键字中, 并用逗号 (u + 002C) 和空格 (u + 0020) 分隔每个关键字。 MIME 编写器可能会删除该属性, 而不是将其复制到关键字标头字段, 以避免不同组织中不同类别集之间发生冲突。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为邮件对象。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

