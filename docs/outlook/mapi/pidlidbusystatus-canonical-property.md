---
title: PidLidBusyStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidBusyStatus
api_type:
- COM
ms.assetid: 50c91fe6-2a61-4348-a16d-fd5c501b0715
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cb73a0e09436177b8b53a05588508886ee28a0a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342026"
---
# <a name="pidlidbusystatus-canonical-property"></a>PidLidBusyStatus 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表示用户能否进行约会。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidBusyStatus  <br/> |
|属性集：  <br/> |PSETID_Appointment  <br/> |
|LONG ID (的一) ：  <br/> |0x00008205  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |日历  <br/> |
   
## <a name="remarks"></a>备注

此属性指定对象描述的事件的用户可用性，并且必须是下面指定的值之一。
  
|**值**|**说明**|
|:-----|:-----|
|0x00000000  <br/> |用户可用。  <br/> |
|0x00000001  <br/> |用户已计划暂定事件。  <br/> |
|0x00000002  <br/> |用户正忙。  <br/> |
|0x00000003  <br/> |用户不在办公室。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

