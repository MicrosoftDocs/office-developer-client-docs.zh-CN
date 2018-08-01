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
ms.openlocfilehash: ce7f7e2db341be62912935b7a55d69eaf5db8ab5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774697"
---
# <a name="copying-address-book-entries"></a>复制通讯簿条目

  
  
**适用于**： Outlook 
  
时调用容器的[IABContainer::CopyEntries](iabcontainer-copyentries.md)方法从相同的一个或多个收件人或另一个容器的复制到此容器。 **CopyEntries**具有四个输入的参数： 表示要复制的收件人的项标识符、 窗口句柄进度指示器、 进度对象指针，和一个标志值的数组。 如果 AB_NO_DIALOG 标志未设置和使用_lpProgress_参数中的进度对象，如果不为 NULL，则您的提供商应显示进度。 如果_lpProgress_为 NULL，则调用[IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)使用 MAPI 进度对象。 有关显示进度的详细信息，请参阅[显示进度指示器](mapi-progress-indicators.md)。
  
除了 AB_NO_DIALOG 禁止进度指示器，两个其他标志之一可以设置为请求的重复项检查类型： CREATE_CHECK_DUP_LOOSE 或 CREATE_CHECK_DUP_STRICT。 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志是仅来对您的提供程序如何确定重复项的建议，可以忽略。 MAPI 建议，您的提供商实现这些标志的支持，如下所示。
  
|**重复项标志**|**建议的实现**|
|:-----|:-----|
|CREATE_CHECK_DUP_LOOSE  <br/> |检查是否要创建的项的显示名称匹配项已在容器的显示名称。  <br/> |
|CREATE_CHECK_DUP_STRICT  <br/> |检查的显示名称和要创建的项中的搜索键匹配容器条目的显示名称和搜索键。  <br/> |
   
最后一个标志，CREATE_REPLACE，指示新条目应替换现有的场，是否您的提供商已确定要创建一个条目已在您的容器的条目的副本。 
  
如果您的提供商，个人通讯簿中每个复制操作包括**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。 包括详细信息显示表复制收件人的允许您将显示收件人而无需调用原始容器创建显示详细的容器。
  
 **若要实现 IABContainer::CopyEntries**
  
1. 确定_lpEntries_参数中的每个条目标识符是您的提供商处理并不是，如果失败并返回 MAPI_E_INVALID_ENTRYID 的格式。 
    
2. 如果条目标识符表示消息的用户、 通讯组列表或提供程序处理的容器：
    
1. 调用您[IMAPISupport::OpenEntry](imapisupport-openentry.md)方法以打开对应的收件人。 
    
2. 将收件人复制到您的容器。 
    
3. 如果条目标识符代表外的收件人：
    
1. 调用容器的[IABContainer::CreateEntry](iabcontainer-createentry.md)方法创建一个新收件人。 
    
2. 设置新收件人初始属性。
    
4. 调用新对象的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法以将其保存。 
    
5. 更新的容器内容表，以反映新收件人。 
    
6. 调用[IMAPISupport::Notify](imapisupport-notify.md)将表通知发送到注册的客户端。 
    

