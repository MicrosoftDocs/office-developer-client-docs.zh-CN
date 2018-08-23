---
title: PidTagRemoteProgress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRemoteProgress
api_type:
- COM
ms.assetid: 01cae79e-5b56-4cd4-83a6-f0956ff539fb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e1f57fd95ff38ef102cd74b0035dbb6b553259c9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569349"
---
# <a name="pidtagremoteprogress-canonical-property"></a>PidTagRemoteProgress 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
此属性包含一个数字，指示远程传输的状态。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_REMOTE_PROGRESS  <br/> |
|标识符：  <br/> |0x3E0B  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>注解

如果没有传输正在进行，则此属性应设置为 1。 如果正在传输，它应从 0 到 100 指示转接的完成百分比设置为值。
  
具有数值状态代码关联的文本显示**PR_REMOTE_PROGRESS_TEXT** ([PidTagRemoteProgressText](pidtagremoteprogresstext-canonical-property.md)) 属性中。
  
可以为此属性设置的以下标记：
  
MSGSTATUS_REMOTE_DELETE
  
> 在传输邮件将被删除。
    
MSGSTATUS_REMOTE_DOWNLOAD
  
> 邮件传输正在进行。
    
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

