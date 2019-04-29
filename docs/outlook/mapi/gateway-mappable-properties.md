---
title: 网关可映射属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3a51ee7e-d030-4f04-915b-ff8bd351207d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6f1a399cac2adbae66dabf9383540bb089424d17
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430474"
---
# <a name="gateway-mappable-properties"></a>网关可映射属性

**适用于**：Outlook 2013 | Outlook 2016 
  
网关可映射属性是指从一个邮件域发送到另一个邮件域时可能需要进行转换的属性。 MAPI 的网关-可映射属性使邮件能够包含需要网关的信息, 以确保目标邮件系统正常使用。 尽管不需要网关开发人员提供此转换功能, 但他们应考虑使用网关可映射属性作为改进邮件内容处理的机会。
  
MAPI 指定了五种类型的网关-映射属性:
  
- 可分辨名称 (DN)
    
- 显示名称
    
- 电子邮件类型
    
- 条目标识符
    
- 搜索关键字
    
这是与收件人、发件人、报告收件人以及委派的发件人和收件人相关联的一组地址属性。 为了帮助您的客户端定义这些属性, 以便网关对它们进行专门处理, MAPI 使用命名属性和属性集指定命名约定。 有五个属性集可用于保留命名属性, 这是需要映射的寻址属性。 为每种类型的类型映射属性设置了一个属性。 将保留这些命名的寻址属性的属性集如下所示。
  
|**属性集**|**说明**|
|:-----|:-----|
|PS_ROUTING_DISPLAY_NAME  <br/> |包含用作显示名称的字符串属性。  <br/> |
|PS_ROUTING_EMAIL_ADDRESSES  <br/> |包含用作电子邮件地址的字符串属性。  <br/> |
|PS_ROUTING_ADDRTYPE  <br/> |包含用作电子邮件地址类型的字符串属性。  <br/> |
|PS_ROUTING_ENTRYID  <br/> |包含用作长期条目标识符的二进制属性。  <br/> |
|PS_ROUTING_SEARCH_KEY  <br/> |包含用作搜索键的二进制属性。  <br/> |
   

