---
title: PidLidSharingProviderGuid 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingProviderGuid
api_type:
- COM
ms.assetid: 103c9cf2-42fb-4fa5-b9c2-8a92725d3097
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 68a1fef672b4f32c6ff0ebfea56bf240b7281f0f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336881"
---
# <a name="pidlidsharingproviderguid-canonical-property"></a>PidLidSharingProviderGuid 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定共享提供程序全局唯一标识符 (GUID)。 这是共享邮件的属性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidSharingProviderGuid  <br/> |
|属性集:  <br/> |PSETID_Sharing  <br/> |
|长 ID (盖子):  <br/> |0x00008A01  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |共享  <br/> |
   
## <a name="remarks"></a>注解

此属性的值必须设置为 "% xAE 0.06.00.00.00.00.00 0.00.00.00.00.00.00.46"。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)
  
> 在客户端之间共享邮箱文件夹。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

