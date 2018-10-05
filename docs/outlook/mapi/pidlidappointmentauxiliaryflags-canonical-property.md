---
title: PidLidAppointmentAuxiliaryFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentAuxiliaryFlags
api_type:
- COM
ms.assetid: 56c64e23-4a99-4f80-ba06-dfae2a5fe961
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4414ae866dece0654131d1575fe699676892709f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396832"
---
# <a name="pidlidappointmentauxiliaryflags-canonical-property"></a>PidLidAppointmentAuxiliaryFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定的描述对象的辅助状态位字段。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidApptAuxFlags  <br/> |
|属性进行设置：  <br/> |PSETID_Appointment  <br/> |
|长 ID （盖）：  <br/> |0x00008207  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |会议  <br/> |
   
## <a name="remarks"></a>说明

此属性不是必需的。 下面是可以设置的单个标记。
  
C (auxApptFlagCopied，0x00000001)
  
> 此标志指示 calendar 对象已复制从另一个日历文件夹。
    
R (auxApptFlagForceMtgResponse，0x00000002:uc)
  
> 在会议请求此标志指示客户端或服务器应发送回组织者的会议响应，如果选择响应。
    
F (auxApptFlagForwarded，0x00000004)
  
> 在会议请求此标志指示它已转发 （包括由组织者转发的），而不是组织者的邀请。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

