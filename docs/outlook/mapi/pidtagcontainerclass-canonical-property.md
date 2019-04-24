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
  
包含描述文件夹类型的文本字符串。 虽然通常忽略此属性, 但在 Exchange server 2003 邮箱管理器之前的 Microsoft ® Exchange server 版本要求此属性存在。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTAINER_CLASS、PR_CONTAINER_CLASS_A、PR_CONTAINER_CLASS_W  <br/> |
|标识符:  <br/> |0x3613  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |Container  <br/> |
   
## <a name="remarks"></a>注解

Exchange Server 通常不使用这些属性。 但是, Microsoft Office Outlook ®会将其附加到邮箱文件夹中。 此外, exchange server 2003 邮箱管理器之前的 exchange server 版本可能会错误地处理不具有这些属性的文件夹。
  
可以将下表中的字符串值分配给这些属性。
  
|**值**|**文件夹的内容**|
|:-----|:-----|
|限.日程  <br/> |约会  <br/> |
|限.信息  <br/> |联系人  <br/> |
|限.日志  <br/> |Outlook 日记条目  <br/> |
|限.便笺  <br/> |邮件和笔记  <br/> |
|限.ipm.stickynote  <br/> |Outlook 粘滞便笺  <br/> |
|限.任务  <br/> |Outlook 任务  <br/> |
   
对于包含邮件的文件夹, 应将这些属性设置为 IPF。便笺.
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)
  
> 指定用于创建和定位邮箱中的特殊文件夹的属性和操作。
    
[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定允许用于联系人和个人通讯组列表对象的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

