---
title: PidLidSharingCapabilities 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingCapabilities
api_type:
- COM
ms.assetid: 86b3eab2-2594-4204-aedf-8ce2ee3b81ce
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d44851e1c863cb117eed3462eb98de87f8d1f0be
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358889"
---
# <a name="pidlidsharingcapabilities-canonical-property"></a>PidLidSharingCapabilities 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定为共享邮件的属性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidSharingCaps  <br/> |
|属性集：  <br/> |PSETID_Sharing  <br/> |
|LONG ID (的一) ：  <br/> |0x00008A17  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |共享  <br/> |
   
## <a name="remarks"></a>备注

此属性必须设置为下列值之一：
  
|**值**|**应用场景**|
|:-----|:-----|
|0x00040290  <br/> |此共享邮件对象与特殊文件夹相关。  <br/> |
|0x000402B0  <br/> |此共享邮件对象与特殊文件夹不相关。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)
  
> 在客户端之间共享邮箱文件夹。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

