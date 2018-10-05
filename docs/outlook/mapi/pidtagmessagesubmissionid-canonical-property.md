---
title: PidTagMessageSubmissionId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageSubmissionId
api_type:
- HeaderDef
ms.assetid: 0a799fe5-04e2-4e1d-b0cd-9bdd2577d299
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 723affa054cb35a9cc7a2ee28e051e3b9a6d04e0
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401662"
---
# <a name="pidtagmessagesubmissionid-canonical-property"></a>PidTagMessageSubmissionId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含的邮件传输代理 (MTA) 的邮件传输系统 (MTS) 标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_SUBMISSION_ID  <br/> |
|标识符：  <br/> |0x0047  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>说明

此属性返回的邮件提交的成功完成后 MTA。 有关此消息，如请求取消 MTA 与任何将来联系人使用此属性中 MTS 标识符。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 进行编码和解码为有效的流表示形式的消息和附件对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

