---
title: PidTagServiceName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagServiceName
api_type:
- COM
ms.assetid: 9a63d647-7504-42fc-b317-6b02b89070eb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e5659113b1c6579913042ae0c8dfcd03e9802621
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438958"
---
# <a name="pidtagservicename-canonical-property"></a>PidTagServiceName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用户在 MapiSvc.inf 文件中设置的邮件服务的名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SERVICE_NAME、PR_SERVICE_NAME_A、PR_SERVICE_NAME_W  <br/> |
|标识符:  <br/> |0x3D09  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 配置文件  <br/> |
   
## <a name="remarks"></a>备注

这些属性中包含的名称特定于邮件服务。 它来自 MapiSvc.inf 中的 [Services] 部分。
  
这些属性在邮件服务表中显示为列，可用于筛选服务。 由于该值用于标识和筛选服务，因此不应本地化该值。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

