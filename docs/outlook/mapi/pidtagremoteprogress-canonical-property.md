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
ms.openlocfilehash: a5a9d0796bc92514ae6d990b7328364b85bc55cd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439840"
---
# <a name="pidtagremoteprogress-canonical-property"></a>PidTagRemoteProgress 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
此属性包含一个指示远程传输的状态的数字。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_REMOTE_PROGRESS  <br/> |
|标识符:  <br/> |0x3E0B  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>说明

如果没有进行传输, 应将此属性设置为1。 如果正在进行传送, 则应将其设置为介于0到100之间的值, 表示传输完成百分比。
  
与数值状态代码关联的文本显示在**PR_REMOTE_PROGRESS_TEXT** ([PidTagRemoteProgressText](pidtagremoteprogresstext-canonical-property.md)) 属性中。
  
可以为此属性设置以下标志:
  
MSGSTATUS_REMOTE_DELETE
  
> 邮件传输已删除。
    
MSGSTATUS_REMOTE_DOWNLOAD
  
> 正在进行邮件传输。
    
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

