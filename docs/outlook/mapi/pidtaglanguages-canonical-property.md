---
title: PidTagLanguages 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagLanguages
api_type:
- HeaderDef
ms.assetid: 16d4e92d-d48e-4e06-9886-2d21f3d10640
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f3d8693644020dd77877db219b000f8f8c804376
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417838"
---
# <a name="pidtaglanguages-canonical-property"></a>PidTagLanguages 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含在邮件中并入的语言的 ASCII 列表。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_LANGUAGES、PR_LANGUAGES_A、PR_LANGUAGES_W  <br/> |
|标识符:  <br/> |0x002F  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |常规邮件  <br/> |
   
## <a name="remarks"></a>说明

这些属性包含由逗号分隔的双字符国家/地区代码的序列。 
  
## <a name="related-resources"></a>相关资源

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

