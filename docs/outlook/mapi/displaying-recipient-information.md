---
title: 显示收件人信息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7ffec274-ee90-44c7-ab2e-7dfb502517a6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e1c31e5edf702dd8f172f67e7055a96ae4cfff1c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412952"
---
# <a name="displaying-recipient-information"></a>显示收件人信息

**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 提供了一个用于显示收件人详细信息的通用对话框。 "详细信息" 对话框是从显示表和**IMAPIProp**实现创建的。 显示表描述了详细信息显示和**IMAPIProp**实现控制收件人的数据的外观。 提供程序负责为每个收件人提供显示表和**IMAPIProp**实现。 
  
创建显示表的最简单方法是定义[DTPAGE](dtpage.md)结构并调用[BuildDisplayTable](builddisplaytable.md)。 但是, 某些提供程序是只读提供程序, 允许创建一次性收件人, 请使用**IPropData**。 **IMAPIProp**实现可以是任何类型的属性对象。 
  
有两种方法可以调用此对话框: [IAddrBook::D etails](iaddrbook-details.md)和[IMAPISupport::D etails](imapisupport-details.md)。 当提供程序调用这些方法之一来请求获取收件人的详细信息时, MAPI 首先通过调用其容器的[IMAPIContainer:: OpenEntry](imapicontainer-openentry.md)方法来打开收件人。 接下来, 它调用收件人的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法来请求**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。 **PR_DETAILS_TABLE**是代表收件人的详细信息显示表的属性。 
  
[IPropData: IMAPIProp](ipropdataimapiprop.md)接口可用于监视显示表控件的更改, 如下面的过程所述。 
  
## <a name="monitor-changes-to-a-control"></a>监视对控件的更改
  
1. 在用户获得对控件的访问权限之前, 请调用[IPropData:: HrSetObjAccess](ipropdata-hrsetobjaccess.md)将控件的访问权限设置为 IPROP_CLEAN。 
    
2. 允许用户使用对话框。 
    
3. 当用户完成时, 调用[IPropData:: HrGetPropAccess](ipropdata-hrgetpropaccess.md)以检索控件的当前访问级别。 
    
4. 如果访问级别为 IPROP_DIRTY, 则用户修改了控件。 您的提供商应执行以下操作:
    
   - 调用[IPropData:: HrSetPropAccess](ipropdata-hrsetpropaccess.md)以将访问级别设置回 IPROP_CLEAN。 
    
   - 调用属性数据对象的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索已更改的属性并通过调用[IMAPIProp:: SetProps](imapiprop-setprops.md)对其进行更新。
    
5. 如果访问级别仍为 IPROP_CLEAN, 则该控件尚未修改。 
    
有关创建显示表的详细信息, 请参阅[显示表](display-tables.md)。
  

