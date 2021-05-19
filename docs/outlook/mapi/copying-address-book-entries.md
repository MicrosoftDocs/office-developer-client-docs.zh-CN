---
title: 复制通讯簿条目
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 285abeb4-45c8-4e82-9a16-b935b4651afe
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 190c4bf12c8f5aaaf8143f59239bb53fb68046f5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418741"
---
# <a name="copying-address-book-entries"></a>复制通讯簿条目

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将同一容器或另一个容器中的一个或多个收件人复制到此容器中时，将调用容器的 [IABContainer：：CopyEntries](iabcontainer-copyentries.md) 方法。 **CopyEntries** 有四个输入参数：表示要复制的收件人的条目标识符数组、进度指示器的窗口句柄、进度对象指针和标志值。 如果未设置 AB_NO_DIALOG，则提供程序应显示进度，如果未为 NULL，则使用  _lpProgress_ 参数中的 progress 对象。 如果  _lpProgress_ 为 NULL，则调用 [IMAPISupport：:D oProgressDialog](imapisupport-doprogressdialog.md) 以使用 MAPI 进度对象。 有关显示进度的信息，请参阅 [显示进度指示器](mapi-progress-indicators.md)。
  
除了AB_NO_DIALOG进度指示器之外，还可以设置其他两个标志之一以请求重复项检查的类型：CREATE_CHECK_DUP_LOOSE 或 CREATE_CHECK_DUP_STRICT。 这些CREATE_CHECK_DUP_LOOSE CREATE_CHECK_DUP_STRICT标记只是有关提供程序如何确定重复条目的建议，可以忽略。 MAPI 建议提供程序实现对这些标志的支持，如下所示。
  
|**重复的条目标志**|**建议的实现**|
|:-----|:-----|
|CREATE_CHECK_DUP_LOOSE  <br/> |检查要显示名称条目中的项是否与显示名称中已有条目的匹配。  <br/> |
|CREATE_CHECK_DUP_STRICT  <br/> |检查要创建的显示名称中的搜索键和搜索键是否显示名称项的搜索键匹配。  <br/> |
   
最后一个标志 CREATE_REPLACE 指示，如果提供程序已确定要创建的条目是容器中已存在的条目的重复项，则新条目应替换现有的条目。 
  
如果您的提供程序是个人通讯簿，则每个复制PR_DETAILS_TABLE ( [PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。 通过包括已复制收件人的详细信息显示表，您的容器可以显示收件人的详细信息，而不必调用原始容器来创建显示。
  
 **实现 IABContainer：：CopyEntries**
  
1. 确定  _lpEntries_ 参数中的每个条目标识符是否采用提供程序处理的格式，如果未采用，则失败并返回MAPI_E_INVALID_ENTRYID。 
    
2. 如果条目标识符表示提供程序处理的消息用户、通讯组列表或容器：
    
1. 调用 [IMAPISupport：：OpenEntry](imapisupport-openentry.md) 方法以打开相应的收件人。 
    
2. 将收件人复制到容器。 
    
3. 如果条目标识符表示一个外收件人：
    
1. 调用容器的 [IABContainer：：CreateEntry](iabcontainer-createentry.md) 方法以创建新收件人。 
    
2. 设置新收件人的初始属性。
    
4. 调用新对象的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法来保存它。 
    
5. 更新容器的内容表以反映新收件人。 
    
6. 调用 [IMAPISupport：：Notify](imapisupport-notify.md) 以向注册的客户端发送表通知。 
    

