---
title: PidTagAttachNumber 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachNumber
api_type:
- HeaderDef
ms.assetid: 507e0f2c-383c-4e2f-917b-159913f7234d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 474ffaf2317cadd214074419f09bb913b1eee4ff
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327249"
---
# <a name="pidtagattachnumber-canonical-property"></a>PidTagAttachNumber 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个唯一标识其父邮件中的附件的编号。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_NUM  <br/> |
|标识符:  <br/> |0x0E21  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>备注

邮件存储将生成和维护此属性。 附件编号是附件表中呈现位置后的辅助排序键。 
  
 **PR_ATTACH_NUM** [IMessage：：OpenAttach 方法打开附件](imessage-openattach.md) 。 在客户端应用程序的会话中，只要PR_ATTACH_NUM表处于打开状态，邮件附件的 PR_ATTACH_NUM 属性就保持不变。 
  
邮件存储使用 **IMessage：：CreateAttach** 和 **IMessage：:D eleteAttach** 方法将更改传播到表。 邮件存储可以选择在打开的附件表上生成表通知，以便客户端可以重新同步这些更改。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

