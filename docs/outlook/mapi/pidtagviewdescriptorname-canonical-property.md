---
title: PidTagViewDescriptorName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagViewDescriptorName
api_type:
- COM
ms.assetid: 1e689ee4-9e89-4328-beb9-05c80a6544a0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ab906d83ae4ad46747fd9037728620db1d656d25
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394767"
---
# <a name="pidtagviewdescriptorname-canonical-property"></a>PidTagViewDescriptorName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含视图描述符的名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_VD_NAME，PR_VD_NAME_A，PR_VD_NAME_W  <br/> |
|标识符：  <br/> |0x7006  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |类定义消息可传送  <br/> |
   
## <a name="remarks"></a>说明

这些属性必须设置为包含视图定义的文件夹关联的信息 （从故障） 消息的非空字符串。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXOCFG]](https://msdn.microsoft.com/library/7d466dd5-c156-4da9-9a01-75c78e7e1a67%28Office.15%29.aspx)
  
> 指定的位置和客户端和服务器配置数据，如共享的类别列表和工作时间的属性。
    
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

