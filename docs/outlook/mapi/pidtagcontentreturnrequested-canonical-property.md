---
title: PidTagContentReturnRequested 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContentReturnRequested
api_type:
- HeaderDef
ms.assetid: f86f7c59-42ab-4ac0-80fe-c985103e6bd6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c64288f393f15ee330065a43a92930f2e6f4e134
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419770"
---
# <a name="pidtagcontentreturnrequested-canonical-property"></a>PidTagContentReturnRequested 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果邮件应返回 nondelivery 报告, 则该参数包含 TRUE。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTENT_RETURN_REQUESTED  <br/> |
|标识符:  <br/> |0x000A  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |报告  <br/> |
   
## <a name="remarks"></a>说明

如果未设置此属性, 则 MAPI 会将其视为具有真正的值。 
  
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

