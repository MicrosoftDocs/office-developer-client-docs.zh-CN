---
title: PidTagDistributionListExpansionHistory 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDistributionListExpansionHistory
api_type:
- HeaderDef
ms.assetid: fc1e0162-d655-4761-92e7-b469579c270b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a172fa1e04f1ea50c29955febda47be6e52663b4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360751"
---
# <a name="pidtagdistributionlistexpansionhistory-canonical-property"></a>PidTagDistributionListExpansionHistory 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含演示如何在邮件传输过程中扩展通讯组列表的历史记录。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DL_EXPANSION_HISTORY  <br/> |
|标识符:  <br/> |0x0013  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>注解

如果传输提供程序已对其进行设置, 则可使用此属性接收客户端应用程序。 如果邮件内容随报告一起返回, 则发送客户端也可使用它。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagDistributionListExpansionProhibited 规范属性](pidtagdistributionlistexpansionprohibited-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

