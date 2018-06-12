---
title: PidTagRecipientTrackStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientTrackStatus
api_type:
- COM
ms.assetid: d619b5e7-2867-44fc-9b42-123bb1bf7bde
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: cbc934eec5331a0302ba222108ee92a0dc696b1f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778176"
---
# <a name="pidtagrecipienttrackstatus-canonical-property"></a>PidTagRecipientTrackStatus 规范属性

  
  
**适用于**： Outlook 
  
指示参与者返回的响应状态。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_RECIPIENT_TRACKSTATUS  <br/> |
|标识符:  <br/> |0x5FFF  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |传输收件人  <br/> |
   
## <a name="remarks"></a>备注

如果未设置此值，它必须假定为 respNone。 否则，它必须是下列选项之一：
  
|**响应状态**|**值**|**说明**|
|:-----|:-----|:-----|
|respNone  <br/> |0x00000000  <br/> |没有响应，则需要此对象。 这是约会对象和会议响应对象的情况。  <br/> |
|respTentative  <br/> |0x00000002  <br/> |与会者的会议对象上的此值指示与会者已暂时接受会议请求对象。  <br/> |
|respAccepted  <br/> |0x00000003  <br/> |与会者的会议对象上的此值指示参与者已接受会议请求对象。  <br/> |
|respDeclined  <br/> |0x00000004  <br/> |与会者的会议对象上的此值指示参与者已拒绝会议请求对象。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

