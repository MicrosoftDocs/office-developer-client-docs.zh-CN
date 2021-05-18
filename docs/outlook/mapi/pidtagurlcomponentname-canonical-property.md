---
title: PidTagUrlComponentName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagUrlComponentName
api_type:
- COM
ms.assetid: a21906f9-5408-41ba-a89b-273ab60eeef3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 26a9d432d98c546aefa8f511ba2c4c9bb26cfd80
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320424"
---
# <a name="pidtagurlcomponentname-canonical-property"></a>PidTagUrlComponentName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件的 URL 组件名称。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_URL_COMP_NAME、PR_URL_COMP_NAME_A、PR_URL_COMP_NAME_W  <br/> |
|标识符:  <br/> |0x10F3  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

这些属性在文件夹中应该是唯一的。 如果在创建邮件时未设置，则邮件存储应基于各种邮件属性设置这些属性，具体取决于邮件类。 例如 **，IPM。注意** 和 **IPM。约会** 邮件应基于 [PidTagSubject](pidtagsubject-canonical-property.md)属性和 IPM PR_SUBJECT (属性) 设置 **此属性。联系人** 邮件应基于 [PidLidFileUnder](pidlidfileunder-canonical-property.md)属性的 **dispidFileUnder** (设置此属性) 属性。 对于大多数其他邮件类，此属性应基于 PR_DISPLAY_NAME ( [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 将邮件和附件对象编码和解码为有效的流表示形式。
    
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

