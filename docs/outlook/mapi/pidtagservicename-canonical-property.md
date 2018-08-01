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
ms.openlocfilehash: 260a35af11b76b1867c693723c1a7fa8133082fd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778405"
---
# <a name="pidtagservicename-canonical-property"></a>PidTagServiceName 规范属性

  
  
**适用于**： Outlook 
  
包含由 MapiSvc.inf 文件中的用户设置消息服务的名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SERVICE_NAME，PR_SERVICE_NAME_A，PR_SERVICE_NAME_W  <br/> |
|标识符：  <br/> |0x3D09  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 配置文件  <br/> |
   
## <a name="remarks"></a>说明

这些属性中包含的名称是特定于邮件服务。 来自 MapiSvc.inf 中的 [服务] 一节。
  
这些属性显示为邮件服务表中的列，并且可用于筛选的服务。 因为它用于标识和筛选服务，不应本地化值。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

