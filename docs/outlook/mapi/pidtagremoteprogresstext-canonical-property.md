---
title: PidTagRemoteProgressText 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRemoteProgressText
api_type:
- COM
ms.assetid: b74d4350-4ad6-4c3f-8326-bd28537dfa0f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0a9d6bbe6807c2893c1bb208976dae9e695aa125
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592800"
---
# <a name="pidtagremoteprogresstext-canonical-property"></a>PidTagRemoteProgressText 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
此属性包含一个字符串，指示远程传输的状态。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_REMOTE_PROGRESS_TEXT，PR_REMOTE_PROGRESS_TEXT_A，PR_REMOTE_PROGRESS_TEXT_W  <br/> |
|标识符：  <br/> |0x3E0C  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>注解

与此文本相关联的数字代码传递**PR_REMOTE_PROGRESS** ([PidTagRemoteProgress](pidtagremoteprogress-canonical-property.md)) 属性中。
  
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

