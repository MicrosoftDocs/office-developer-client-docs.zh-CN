---
title: PidLidCustomFlag 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidCustomFlag
api_type:
- COM
ms.assetid: bfb7fd1e-774f-9a2f-fbbe-ba7f68ed8663
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9a131c633b8dcf9b0e5070f01de8fcab90a18ade
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357615"
---
# <a name="pidlidcustomflag-canonical-property"></a>PidLidCustomFlag 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
一个位掩码，指定如何自定义邮件，例如，与自定义属性一起保存。
  
## 

|||
|:-----|:-----|
|相关属性：  <br/> |dispidCustomFlag  <br/> |
|LONG ID (的一) ：  <br/> |0x00008251  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
   
## <a name="remarks"></a>备注

若要检索此属性的值，首先使用 **[IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md)** 获取属性标记，然后在 **[IMAPIProp：：GetProps](imapiprop-getprops.md)** 中指定此属性标记以获取值。 
  
可能的标志如下所示：
  
****

|**常量**|**值**|
|:-----|:-----|
|INSP_ONEOFFFLAGS  <br/> |0x0D000000  <br/> |
|INSP_PROPDEFINITION  <br/> |0x02000000  <br/> |
   
调用 **IMAPIProp：：GetIDsFromNames** 时，为输入参数 *lppPropNames* 指向的 **[MAPINAMEID](mapinameid.md)** 结构指定以下值。 
  
****

|**成员**|**值**|
|:-----|:-----|
|lpGuid：  <br/> |PSETID_Common  <br/> |
|ulKind：  <br/> |MNID_ID  <br/> |
|Kind.lID：  <br/> |dispidCustomFlag  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义。
    
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

