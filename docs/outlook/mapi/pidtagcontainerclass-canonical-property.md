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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400255"
---
# <a name="pidtagcontainerclass-canonical-property"></a>PidTagContainerClass 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含描述文件夹的类型的文本字符串。 通常，则忽略此属性，尽管版本的 Exchange Server 2003 邮箱管理器之前的 Microsoft® Exchange Server 希望此属性才存在此参数。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTAINER_CLASS，PR_CONTAINER_CLASS_A，PR_CONTAINER_CLASS_W  <br/> |
|标识符：  <br/> |0x3613  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |Container  <br/> |
   
## <a name="remarks"></a>说明

这些属性通常不使用 Exchange Server。 但是，Microsoft Office Outlook® 将它们附加到邮箱文件夹。 此外，版本的 Exchange Server 2003 邮箱管理器之前的 Exchange Server 可能会错误地处理不具有这些属性的文件夹。
  
下表中的字符串值，可以分配这些属性。
  
|**值**|**文件夹的内容**|
|:-----|:-----|
|IPF。约会  <br/> |约会  <br/> |
|IPF。联系人  <br/> |联系人  <br/> |
|IPF。日记  <br/> |Outlook 日记条目  <br/> |
|IPF。注释  <br/> |邮件和注释  <br/> |
|IPF。便笺  <br/> |Outlook 粘滞便笺  <br/> |
|IPF。任务  <br/> |Outlook 任务  <br/> |
   
对于包含邮件的文件夹，这些属性应设置为 IPF。请注意。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)
  
> 指定的属性和用于创建和邮箱中查找的特殊文件夹的操作。
    
[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定的属性和允许的联系人和个人通讯组列表对象的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

