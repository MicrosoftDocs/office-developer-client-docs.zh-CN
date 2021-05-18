---
title: PidTagAccount 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAccount
api_type:
- HeaderDef
ms.assetid: bec199b5-abfd-4686-ad59-21092212e1a5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2962f973aa87b88f237ded69573df9ef312a7bc5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359776"
---
# <a name="pidtagaccount-canonical-property"></a>PidTagAccount 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含收件人的帐户名称。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ACCOUNT、PR_ACCOUNT_A、PR_ACCOUNT_W  <br/> |
|标识符:  <br/> |0x3A00  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>备注

这些属性为收件人提供标识和访问信息。 它们由收件人及其组织定义。
  
这些属性通常包含收件人的电子邮件名称，即电子邮件地址的最后一个组件，用于唯一标识本地组织中收件人。 电子邮件名称对应于 X.400 可分辨名称，该名称是保证在特定邮件域中唯一的短名称。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定联系人和个人通讯组列表允许的属性和操作。
    
[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源的列表的属性和操作。
    
### <a name="header-files"></a>头文件

mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[IMailUser : IMAPIProp](imailuserimapiprop.md)


[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

