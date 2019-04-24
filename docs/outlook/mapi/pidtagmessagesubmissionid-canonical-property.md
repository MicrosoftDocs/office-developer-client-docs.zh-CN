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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329398"
---
# <a name="pidtagmessagesubmissionid-canonical-property"></a>PidTagMessageSubmissionId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件传输代理 (MTA) 的邮件传输系统 (MTS) 标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_SUBMISSION_ID  <br/> |
|标识符:  <br/> |0x0047  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>注解

成功完成邮件提交后, MTA 将返回此属性。 与此邮件相关的 MTA 的任何将来联系人 (如请求取消) 将在此属性中使用 MTS 标识符。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 将邮件和附件对象编码并解码为高效流表示形式。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

