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
ms.openlocfilehash: 01d4391850067d00645b5c0248e1bf858c2a9049
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776709"
---
# <a name="pidlidcategories-canonical-property"></a>PidLidCategories 规范属性

  
  
**适用于**： Outlook 
  
指定项目类别的列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidCategories  <br/> |
|属性进行设置：  <br/> |PS_PUBLIC_STRINGS  <br/> |
|长 ID （盖）：  <br/> |0x00002328  <br/> |
|数据类型：  <br/> |PT_MV_UNICODE  <br/> |
|区域：  <br/> |Common  <br/> |
   
## <a name="remarks"></a>说明

若要生成一个关键字标头字段，客户端必须设置为所需的值的此属性的值。 此属性包含多个字符串;每个类别应映射到单个关键字。
  
多用途 Internet 邮件扩展 (MIME) 编写器应将此属性的每个子值复制到单独关键字的关键字标头字段中，使用逗号分隔 (U + 002 C) 和空间 (U + 0020) 分隔每个关键字。 MIME 作者可能会丢失而不是将其复制到关键字标头字段中，为了避免冲突之间的不同组织中的类别的不同设置此属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为消息对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

