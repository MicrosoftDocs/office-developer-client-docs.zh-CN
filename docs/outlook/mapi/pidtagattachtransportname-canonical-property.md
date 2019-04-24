---
title: PidTagAttachTransportName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachTransportName
api_type:
- HeaderDef
ms.assetid: 701fca52-0f96-4019-80cd-c0ccd059ff9b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bd3a22bf55d03f3a9f06bf5c19650407bcc5627d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361066"
---
# <a name="pidtagattachtransportname-canonical-property"></a>PidTagAttachTransportName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含修改的附件文件的名称, 以便可以将其与 TNEF 邮件相关联。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_TRANSPORT_NAME、PR_ATTACH_TRANSPORT_NAME_A、PR_ATTACH_TRANSPORT_NAME_W  <br/> |
|标识符:  <br/> |0x370C  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>注解

TNEF 和传输提供程序使用这些属性。 它们通常对客户端应用程序不可用。 
  
当基础邮件系统不支持提供的文件名时, TNEF 通常会使用这些属性。 例如, 当用户附加多个具有相同名称的文件 (如5个名为 CONFIG 的文件) 时, 将使用这些文件。http.sys. 传输提供程序必须修改名称以确保它们是唯一的。 每个修改的名称都会显示在其附件的**PR_ATTACH_TRANSPORT_NAME**和关联属性中。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
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

