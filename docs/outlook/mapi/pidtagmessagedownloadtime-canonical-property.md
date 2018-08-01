---
title: PidTagMessageDownloadTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageDownloadTime
api_type:
- HeaderDef
ms.assetid: f0d34dd6-7ddb-4843-b848-c89923ff80cc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b47d104ade6a7d23f5630d15697b330360d027b9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777849"
---
# <a name="pidtagmessagedownloadtime-canonical-property"></a>PidTagMessageDownloadTime 规范属性

  
  
**适用于**： Outlook 
  
包含要从远程服务器的邮件下载到本地邮件存储的估计的时间。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_DOWNLOAD_TIME  <br/> |
|标识符：  <br/> |0x0E18  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>说明

此属性以秒为单位表示并代表时间也很远程传输提供程序从其当前位置的给定的邮件下载到的消息存储本地到客户端查看标头文件夹的最佳估计值。 远程传输提供程序通常由**PR_MESSAGE_SIZE** ([PidTagMessageSize](pidtagmessagesize-canonical-property.md)) 属性的值除以中每秒字节数的 communications 链接的速度计算此属性的值。 如果提供程序无法计算下载时间，例如，如果不知道的链接速度，它应提供此列标题文件夹内容表中如**MAPI_E_NO_SUPPORT** **PT_ERROR**值。 
  
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

