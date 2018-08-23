---
title: 显示收件人信息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7ffec274-ee90-44c7-ab2e-7dfb502517a6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4610d9e643541e39144f2af86a2d64928b8e9ca7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591287"
---
# <a name="displaying-recipient-information"></a>显示收件人信息

**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 提供了用于显示收件人的详细信息的常见的对话框。 显示表和**IMAPIProp**实现被创建详细信息对话框。 显示表描述了显示的详细信息的外观和**IMAPIProp**实现收件人控件数据。 您的提供程序负责提供显示表和**IMAPIProp**实现的每个收件人。 
  
创建显示表的最简单方法是定义[DTPAGE](dtpage.md)结构，并调用[BuildDisplayTable](builddisplaytable.md)。 但是，某些提供程序，特别是只读的提供程序允许一次性收件人，创建使用**IPropData**。 **IMAPIProp**实现可以是任何类型的属性对象。 
  
有两种方法来调用此对话框： [IAddrBook::Details](iaddrbook-details.md)和[IMAPISupport::Details](imapisupport-details.md)。 当您的提供商调用以下方法之一来收件人的请求的详细信息时，MAPI 通过调用与其容器的[IMAPIContainer::OpenEntry](imapicontainer-openentry.md)方法首先打开收件人。 接下来，它调用收件人的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法请求**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。 **PR_DETAILS_TABLE**是代表收件人的详细信息显示表格的属性。 
  
[IPropData: IMAPIProp](ipropdataimapiprop.md)接口可用于监视显示表控件上的更改，如下面的过程中所述。 
  
## <a name="monitor-changes-to-a-control"></a>监视器更改为控件
  
1. 用户获得访问控件之前，请调用[IPropData::HrSetObjAccess](ipropdata-hrsetobjaccess.md) IPROP_CLEAN 设置控件的访问。 
    
2. 允许用户使用对话框。 
    
3. 完成用户后，调用[IPropData::HrGetPropAccess](ipropdata-hrgetpropaccess.md)检索控件的当前访问级别。 
    
4. 如果的访问级别，IPROP_DIRTY 已修改的用户控件。 您的提供商应：
    
   - 调用[IPropData::HrSetPropAccess](ipropdata-hrsetpropaccess.md)设置访问级别回 IPROP_CLEAN。 
    
   - 调用的属性数据对象[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索已更改的属性，并通过调用[IMAPIProp::SetProps](imapiprop-setprops.md)对其进行更新。
    
5. 如果的访问级别，仍 IPROP_CLEAN 尚未修改控件。 
    
有关创建显示表的详细信息，请参阅[显示表](display-tables.md)。
  

