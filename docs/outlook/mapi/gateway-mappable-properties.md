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
ms.openlocfilehash: 07c215511f010741e69c08c184df0ca3ce461e13
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583615"
---
# <a name="gateway-mappable-properties"></a>网关可映射属性

**适用于**： Outlook 2013 |Outlook 2016 
  
网关可映射属性是可能需要翻译时从一个消息域发送到其他的属性。 MAPI 的网关可映射属性启用邮件，其中包含正确需要网关，以确保目标邮件系统使用它的信息。 尽管无需网关开发人员提供此转换功能，但他们应考虑网关可映射属性作为有机会来提高处理的消息内容。
  
MAPI 指定五种类型的网关可映射的属性：
  
- 显示名称
    
- 电子邮件地址
    
- 电子邮件类型
    
- 项标识符
    
- 搜索关键字
    
这是一套解决与收件人、 发件人、 报告收件人和委派发件人和收件人关联的属性。 为了帮助您定义这些属性，以便将网关专门处理它们的客户端，MAPI，请指定使用命名的属性和属性集的命名约定。 五个属性集存在用于存放命名的属性，需要映射寻址属性。 没有为每种类型的可映射属性的一个属性。 将保留这些命名寻址属性的属性集如下所示。
  
|**属性集**|**说明**|
|:-----|:-----|
|PS_ROUTING_DISPLAY_NAME  <br/> |包含用作显示名称的字符串属性。  <br/> |
|PS_ROUTING_EMAIL_ADDRESSES  <br/> |包含用作电子邮件地址的字符串属性。  <br/> |
|PS_ROUTING_ADDRTYPE  <br/> |包含字符串属性用作电子邮件地址类型。  <br/> |
|PS_ROUTING_ENTRYID  <br/> |包含用作长期的项标识符的二进制属性。  <br/> |
|PS_ROUTING_SEARCH_KEY  <br/> |包含用作搜索关键字的二进制属性。  <br/> |
   

