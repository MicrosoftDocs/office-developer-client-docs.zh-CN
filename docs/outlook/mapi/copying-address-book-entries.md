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
  
当同一个或另一个容器中的一个或多个收件人要复制到此容器中时, 将调用您的容器的[IABContainer:: CopyEntries](iabcontainer-copyentries.md)方法。 **CopyEntries**有四个输入参数: 条目标识符的数组, 用于表示要复制的收件人、进度指示器的窗口句柄、进度对象指针和标志值。 如果未设置 AB_NO_DIALOG 标志, 则提供程序应显示进度, 如果不是 NULL, 则使用_lpProgress_参数中的进度对象。 如果_lpProgress_为 NULL, 则调用[IMAPISupport::D oprogressdialog](imapisupport-doprogressdialog.md)以使用 MAPI 进度对象。 有关显示进度的详细信息, 请参阅[显示进度指示器](mapi-progress-indicators.md)。
  
除了 AB_NO_DIALOG 以取消进度指示器之外, 还可以设置两个其他标志之一, 以请求重复项检查的类型: CREATE_CHECK_DUP_LOOSE 或 CREATE_CHECK_DUP_STRICT。 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志仅提供了有关提供程序如何确定重复条目并可被忽略的建议。 MAPI 建议提供程序实现对这些标志的支持, 如下所示。
  
|**重复条目标志**|**建议的实现**|
|:-----|:-----|
|CREATE_CHECK_DUP_LOOSE  <br/> |检查要创建的条目中的显示名称是否与容器中已有条目的显示名称相匹配。  <br/> |
|CREATE_CHECK_DUP_STRICT  <br/> |检查要创建的项中的显示名称和搜索关键字是否与容器项的显示名称和搜索关键字相匹配。  <br/> |
   
最后一个标志 CREATE_REPLACE, 指示如果您的提供程序已确定要创建的项与容器中已有的条目重复, 则新条目应替换现有的条目。 
  
如果您的提供商是个人通讯簿, 请在每个复制操作中包括**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。 包括复制的收件人的详细信息显示表使您的容器能够显示收件人的详细信息, 而无需调用原始容器来创建显示。
  
 **实现 IABContainer:: CopyEntries**
  
1. 确定_lpEntries_参数中的每个条目标识符是否采用提供程序处理的格式, 如果不是, 则会失败并返回 MAPI_E_INVALID_ENTRYID。 
    
2. 如果条目标识符表示提供程序处理的邮件用户、通讯组列表或容器:
    
1. 调用[IMAPISupport:: OpenEntry](imapisupport-openentry.md)方法打开相应的收件人。 
    
2. 将收件人复制到容器。 
    
3. 如果条目标识符代表一个外部收件人:
    
1. 调用容器的[IABContainer:: CreateEntry](iabcontainer-createentry.md)方法以创建新的收件人。 
    
2. 设置新收件人的初始属性。
    
4. 调用新对象的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法以保存它。 
    
5. 更新容器的内容表以反映新的收件人。 
    
6. 调用[IMAPISupport:: Notify](imapisupport-notify.md)向已注册的客户端发送表通知。 
    

