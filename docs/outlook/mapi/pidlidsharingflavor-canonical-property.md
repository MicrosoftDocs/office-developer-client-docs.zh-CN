---
title: PidLidSharingF功能or 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingFlavor
api_type:
- COM
ms.assetid: c91ab5c7-82ac-4895-bf54-2863ca5e2410
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 21144af15e7a36f54af3032f735c391b3038305b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327480"
---
# <a name="pidlidsharingflavor-canonical-property"></a>PidLidSharingF功能or 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定为共享邮件的属性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidSharingF一体机  <br/> |
|属性集：  <br/> |PSETID_Sharing  <br/> |
|LONG ID (的一) ：  <br/> |0x00008A18  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |共享  <br/> |
   
## <a name="remarks"></a>备注

此属性的值必须是下列值之一：
  
|**值**|**共享邮件对象的类型**|
|:-----|:-----|
|0x00020310  <br/> |特殊文件夹的共享邀请。  <br/> |
|0x00000310  <br/> |非特殊文件夹的文件夹的共享邀请。  <br/> |
|0x00020500  <br/> |共享请求。  <br/> |
|0x00020710  <br/> |特殊文件夹的共享邀请和收件人的等效特殊文件夹的共享请求。  <br/> |
|0x00025100  <br/> |拒绝请求的共享响应。  <br/> |
|0x00023310  <br/> |接受请求的共享 (也是一种共享邀请) 。  <br/> |
   
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

