---
title: PidLidInternetAccountName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidInternetAccountName
api_type:
- COM
ms.assetid: 29bedadf-903d-419d-804d-dc8bd92b745d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2da826fe7ab9e4d7ca3eaaf0f9806193c47100d1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315489"
---
# <a name="pidlidinternetaccountname-canonical-property"></a>PidLidInternetAccountName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定发送电子邮件的用户可见的电子邮件帐户名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidInetAcctName  <br/> |
|属性集：  <br/> |PSETID_Common  <br/> |
|LONG ID (的一) ：  <br/> |0x00008580  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

此字符串的格式依赖于实现。 客户端可以使用此属性来确定邮件要发送到的服务器，但是可选的，并且该值对服务器没有任何意义。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定电子邮件对象允许的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

