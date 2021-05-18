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
ms.openlocfilehash: 8078d31af497a437c983da7447a0aebbdfb643fb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407926"
---
# <a name="pidtagmessagedownloadtime-canonical-property"></a>PidTagMessageDownloadTime 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含将邮件从远程服务器下载到本地邮件存储的估计时间。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_DOWNLOAD_TIME  <br/> |
|标识符:  <br/> |0x0E18  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

此属性以秒表示，表示远程传输提供程序将给定邮件从当前位置下载到客户端查看头文件夹的本地邮件存储所花的最佳估计时间。 远程传输提供程序通常通过将 **PR_MESSAGE_SIZE** ([PidTagMessageSize](pidtagmessagesize-canonical-property.md)) 属性的值除以通信链接的速度（以字节/秒为单位）来计算此属性的值。 如果提供程序无法计算下载时间，例如，如果不知道链接速度，则应该提供 **PT_ERROR** 值（如 **MAPI_E_NO_SUPPORT）** 作为标题文件夹内容表中的此列。 
  
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

