---
title: PidLidSharingRemoteType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingRemoteType
api_type:
- COM
ms.assetid: e9bc7c7c-86df-45d8-922b-76e3b076144a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3297ca951097c9f3601086809c6e294854c88656
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331206"
---
# <a name="pidlidsharingremotetype-canonical-property"></a>PidLidSharingRemoteType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定远程共享文件夹的类型。 这是共享邮件的属性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidSharingRemoteType  <br/> |
|属性集：  <br/> |PSETID_Sharing  <br/> |
|LONG ID (的一) ：  <br/> |0x00008A1D  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |共享  <br/> |
   
## <a name="remarks"></a>备注

此属性必须设置为 **与 dispidSharingLocalType** ([PidLidSharingLocalType](pidlidsharinglocaltype-canonical-property.md)) 相同的值，并且应忽略。
  
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

