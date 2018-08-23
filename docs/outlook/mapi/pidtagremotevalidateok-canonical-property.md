---
title: PidTagRemoteValidateOk 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRemoteValidateOk
api_type:
- COM
ms.assetid: e336d2ec-57cb-4d08-bd6e-330ef7d9939e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9b06ebbe8cb162d77d60cfffa866438567c84c27
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576832"
---
# <a name="pidtagremotevalidateok-canonical-property"></a>PidTagRemoteValidateOk 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
此属性包含 TRUE 如果允许远程查看器调用[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_REMOTE_VALIDATE_OK  <br/> |
|标识符：  <br/> |0x3E0D  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>注解

此属性将状态表中显示，并提供一些控制传输性能。 它可以将其视为另一种用于为空闲远程查看器。 当设置为 TRUE 时，远程查看器可以根据需要通常调用**IMAPIStatus::ValidateState** 。 值为 FALSE 指示远程查看器无法进行任何其他呼叫。 
  
传输提供程序通常将该属性设置动态，值设置为 FALSE 可禁用其他呼叫时的传输提供程序具有足够的执行的处理。 完成传输提供程序后，它然后将值设置为 TRUE 以允许客户端应用程序进行进一步**IMAPIStatus::ValidateState**呼叫。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

