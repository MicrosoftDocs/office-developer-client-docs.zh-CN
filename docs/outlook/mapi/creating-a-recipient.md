---
title: 创建收件人
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 586c901f-d9f9-44f2-a328-051775a81265
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e14430d1539b90e089a9dabe1315384050f3dd5e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332954"
---
# <a name="creating-a-recipient"></a>创建收件人

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端在对邮件进行寻址以及将条目添加到可修改通讯簿容器时创建收件人。 MAPI 提供了三种创建收件人的方法:
  
- [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)
    
- [IAddrBook::NewEntry](iaddrbook-newentry.md)
    
- [IABContainer::CreateEntry](iabcontainer-createentry.md)
    
在创建用于处理邮件的收件人时, 调用**IAddrBook:: CreateOneOff** 。 **CreateOneOff**创建一个专门设置的一次性条目标识符, 以与特定地址类型的地址相关联。 有关一次性和一次性条目标识符的详细信息, 请参阅[一次性地址](one-off-addresses.md)和[一次性条目标识符](one-off-entry-identifiers.md)。
  
在创建要用于解决邮件或添加到容器中的收件人时, 调用**IAddrBook:: NewEntry** 。 **NewEntry**具有三对包含条目标识符的参数。 这些参数如下所述: 
  
|**参数对**|**Description**|
|:-----|:-----|
| _cbEidContainer_和_lpEidContainer_ <br/> |应放置新条目的容器的条目标识符。  <br/> |
| _cbEidNewEntryTpl_和_lpEidNewEntryTpl_ <br/> |用于创建新条目的模板的条目标识符。  <br/> |
| _lpcbEidNewEntry_和_lppEidNewEntry_ <br/> |新条目的条目标识符。  <br/> |
   
若要为传出邮件创建收件人, 请将_cbEidContainer_设置为零, 将_lpEidContainer_设置为 NULL。 **NewEntry**创建具有符合一次性格式的条目标识符的收件人, 即调用**IAddrBook:: CreateOneOff**所生成的相同类型的收件人。 
  
若要创建要插入到特定容器中的收件人, 请将_lpEidContainer_的条目标识符和_cbEidContainer_设置为容器条目标识符中的字节数。 
  
若要使用模板创建收件人, 请将_lpEidNewEntryTpl_设置为要使用的模板的条目标识符, 并将_cbEidNewEntryTpl_设置为此条目标识符中的字节数。 大多数可修改的通讯簿容器都支持一个或多个模板来创建特定类型的条目。 一次性模板通常是 (但不总是) 对话框。 将信息输入到模板中时, 将生成一个收件人, 其地址的格式为正确的类型。 
  
从以下任一项获取模板条目标识符:
  
- 容器的一次性表中的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列 (通过调用容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法并指定**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md))) 来访问作为接口标识符的属性标记和 IID_IMAPITable。 
    
- 通讯簿提供程序的**PR_DEF_CREATE_MAILUSER** ([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md)) 和**PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)) 属性, 其中包含提供程序的邮件用户对象的条目标识符和通讯组列表模板。 
    
> [!NOTE]
> 请勿将新条目模板的条目标识符与称为模板标识符的不同类型的条目标识符相混淆。 模板标识符仅由提供程序使用, 用于维护从其他提供程序复制的条目;它从不用于客户端, 它不用于创建新条目。 
  
若要使用户能够确定要创建的条目的类型, 请为_cbEidNewEntryTpl_传递零, 并为_lpEidNewEntryTpl_传递 NULL。 发生这种情况时, **NewEntry**会显示一个内置于 MAPI 一次性表的通用对话框, 即配置文件中每个通讯簿提供程序所支持的所有模板的分层列表。 
  
如果已确定地址类型 (通过_lpEidNewEntryTpl_参数的设置或用户从一次性表格显示的选择), **NewEntry**将使用其显示表显示相应的模板。 所有新的条目模板都支持**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。 
  
若要让**NewEntry**返回已创建条目的条目标识符, 请为_lpcbEidNewEntry_和_lppEidNewEntry_参数传递一个有效的地址。 MAPI 将新条目标识符放在_lppEidNewEntry_所指向的地址和_lpcbEidNewEntry_指向的地址的新条目标识符的字节数。
  
调用[IABContainer:: CreateEntry](iabcontainer-createentry.md)以创建收件人并将其保存到特定的通讯簿容器中。 此方法只能与可修改的容器 (在其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中设置了 AB_MODIFIABLE 标志的容器) 一起使用。 具有不可更改容器的通讯簿提供程序不支持此方法。 指定用于在_lpEntryID_参数中创建所需类型的条目的模板的条目标识符。 
  
在_ulCreateFlags_参数中, 指定所需的重复项检查的类型以及新条目是否应替换现有条目。 如果**CreateEntry**由于提供程序强加的重复条目检查而无法新建对象, 则不会看到返回的错误或警告。 在这些情况下, 提供程序将返回成功代码。 
  
如果要直接使用容器并知道容器可以创建的地址类型, 则可以调用**IABContainer:: CreateEntry**并传递相应模板的条目标识符。 通讯簿提供程序设置一些初始默认属性;您可以调用**SetProps**以设置其他人。 永远不会涉及该用户。 
  

