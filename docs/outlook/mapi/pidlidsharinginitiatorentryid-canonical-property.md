---
title: PidLidSharingInitiatorEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingInitiatorEntryId
api_type:
- COM
ms.assetid: 47f00706-83df-49cb-bda7-ef572d76a020
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bfe682fc3263278c6e1d02a29a8b6432f41ac79e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309525"
---
# <a name="pidlidsharinginitiatorentryid-canonical-property"></a>PidLidSharingInitiatorEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定为共享邮件的属性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidSharingInitiatorEid  <br/> |
|属性集：  <br/> |PSETID_Sharing  <br/> |
|LONG ID (的一) ：  <br/> |0x00008A09  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |共享  <br/> |
   
## <a name="remarks"></a>备注

此属性必须设置为当前登录用户通讯簿的 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的值 (请参阅 [[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)) 。 
  
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

