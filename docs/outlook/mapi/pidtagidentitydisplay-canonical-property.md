---
title: PidTagIdentityDisplay 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIdentityDisplay
api_type:
- HeaderDef
ms.assetid: ad9756c1-c1f9-4ab3-a58a-31e574dd9530
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d6e189f78dec2fc92f1804be93e7885b61734b03
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431419"
---
# <a name="pidtagidentitydisplay-canonical-property"></a>PidTagIdentityDisplay 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含显示名称在邮件系统中定义的服务提供商标识的名称。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_IDENTITY_DISPLAY、PR_IDENTITY_DISPLAY_A、PR_IDENTITY_DISPLAY_W  <br/> |
|标识符:  <br/> |0x3E00  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>备注

这些属性不会在任何对象上显示为属性，而只显示为状态表中的列。 它是公开状态表行的服务提供商标识的一部分。 提供程序的标识通常指其在服务器上的帐户，但可以引用提供程序在邮件系统中定义的任何表示形式。 
  
提供任何标识属性的服务提供商应提供所有标识属性。 属于同一邮件服务的提供程序应公开标识属性的相同值。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IMAPISession::QueryIdentity](imapisession-queryidentity.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

