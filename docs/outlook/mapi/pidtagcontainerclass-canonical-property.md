---
title: PidTagContainerClass 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContainerClass
api_type:
- HeaderDef
ms.assetid: db249e9e-f1f0-4b95-8cd9-daa7c53ddb32
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c5b80831607f473208ce987a720c7e80e44b6d80
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283147"
---
# <a name="pidtagcontainerclass-canonical-property"></a>PidTagContainerClass 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含描述文件夹类型的文本字符串。 尽管通常忽略此属性，® Exchange Server 2003 邮箱管理器Exchange Server Microsoft 2003 之前的版本预期此属性存在。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTAINER_CLASS、PR_CONTAINER_CLASS_A、PR_CONTAINER_CLASS_W  <br/> |
|标识符:  <br/> |0x3613  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |容器  <br/> |
   
## <a name="remarks"></a>备注

这些属性通常不由 Exchange Server。 但是，Microsoft Office Outlook®将它们附加到邮箱文件夹。 此外，Exchange Server 2003 邮箱Exchange Server之前的版本可能无法正确处理没有这些属性的文件夹。
  
可以在下表中为这些属性分配字符串值。
  
|**值**|**文件夹内容**|
|:-----|:-----|
|IPF。约会  <br/> |约会  <br/> |
|IPF。联系人  <br/> |联系人  <br/> |
|IPF。日记  <br/> |Outlook日记条目  <br/> |
|IPF。注意  <br/> |邮件消息和注释  <br/> |
|IPF。StickyNote  <br/> |Outlook 便笺  <br/> |
|IPF。任务  <br/> |Outlook 任务  <br/> |
   
对于包含邮件的文件夹，这些属性应设置为 IPF。注意。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)
  
> 指定用于创建和定位邮箱中特殊文件夹的属性和操作。
    
[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定联系人和个人通讯组列表对象允许的属性和操作。
    
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

