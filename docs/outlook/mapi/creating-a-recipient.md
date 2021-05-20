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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429584"
---
# <a name="creating-a-recipient"></a>创建收件人

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端在设置邮件地址以及将条目添加到可修改通讯簿容器时创建收件人。 MAPI 提供了三种创建收件人的方法：
  
- [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)
    
- [IAddrBook::NewEntry](iaddrbook-newentry.md)
    
- [IABContainer::CreateEntry](iabcontainer-createentry.md)
    
创建用于处理邮件的收件人时，请调用 **IAddrBook：：CreateOneOff。** **CreateOneOff** 创建一个特殊格式的一次输入标识符，该标识符与特定地址类型的地址相关联。 有关一对一条目标识符和一次输入标识符的信息，请参阅 [一](one-off-addresses.md) 次使用地址和 [一次使用条目标识符](one-off-entry-identifiers.md)。
  
创建收件人以用于地址邮件或添加到容器时，请调用 **IAddrBook：：NewEntry。** **NewEntry** 有三对包含条目标识符的参数。 这些参数描述如下： 
  
|**参数对**|**说明**|
|:-----|:-----|
| _cbEidContainer_ 和  _lpEidContainer_ <br/> |新条目应放置到的容器的条目标识符。  <br/> |
| _cbEidNewEntryTpl_ 和  _lpEidNewEntryTpl_ <br/> |用于创建新条目的模板的条目标识符。  <br/> |
| _lpcbEidNewEntry_ 和  _lppEidNewEntry_ <br/> |新条目的条目标识符。  <br/> |
   
若要为传出邮件创建收件人，请设置  _cbEidContainer_ 为零，将  _lpEidContainer 设置为_ NULL。 **NewEntry** 创建一个收件人，其条目标识符符合一次发送格式，即通过调用 **IAddrBook：：CreateOneOff** 生成的相同类型的收件人。 
  
若要创建要插入到特定容器中的收件人，请将  _lpEidContainer_ 设置为容器的条目标识符，将  _cbEidContainer_ 设置为容器的条目标识符中的字节数。 
  
若要使用模板创建收件人，将  _lpEidNewEntryTpl_ 设置为要使用的模板的条目标识符，将  _cbEidNewEntryTpl_ 设置为此条目标识符中的字节数。 大多数可修改通讯簿容器都支持用于创建特定类型条目的一个或多个模板。 一次使用模板通常是（但并不总是）对话框。 在模板中输入信息会生成一个收件人，该收件人的地址类型格式正确。 
  
从以下任一位置获取模板项标识符：
  
- 容器一键式表中的 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列，该列通过调用容器的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法并指定 **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 作为属性标记和 IID_IMAPITable 作为接口标识符来访问。 
    
- 通讯簿提供程序的 **PR_DEF_CREATE_MAILUSER** ([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md)) 和 **PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)) 属性保存提供程序的邮件用户对象和通讯组列表模板的条目标识符。 
    
> [!NOTE]
> 不要将新条目模板的条目标识符与名为模板标识符的不同类型的条目标识符混淆。 模板标识符仅由提供程序用于维护从其他提供程序复制的条目;客户端从不使用，也不用于创建新条目。 
  
若要使用户能够确定要创建的条目的类型，请为  _cbEidNewEntryTpl_ 传递零，为  _lpEidNewEntryTpl_ 传递 NULL。 出现此情况时 **，NewEntry** 将显示一个从 MAPI 的一对一表构建的常见对话框— 配置文件中每个通讯簿提供程序支持的所有模板的分层列表。 
  
在通过  _设置 lpEidNewEntryTpl_ 参数或用户从一次表显示选择的地址类型确定后 **，NewEntry** 会使用其显示表显示相应的模板。 所有新条目模板都支持PR_DETAILS_TABLE ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。 
  
若要让 **NewEntry** 返回所创建条目的条目标识符，请传递  _lpcbEidNewEntry_ 和  _lppEidNewEntry_ 参数的有效地址。 MAPI 将新条目标识符位于  _lppEidNewEntry_ 指向的地址处，新条目标识符的字节计数位于  _lpcbEidNewEntry_ 指向的地址处。
  
调用 [IABContainer：：CreateEntry](iabcontainer-createentry.md) 以创建收件人并将其保存到特定的通讯簿容器中。 只能对可修改的容器（在 PR_CONTAINER_FLAGS ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)属性中设置了 **AB_MODIFIABLE** 标志的容器) 使用此方法。 具有不可修改容器的通讯簿提供程序不支持此方法。 指定模板的条目标识符，以在  _lpEntryID_ 参数中创建所需类型的条目。 
  
在  _ulCreateFlags_ 参数中，指定需要重复项检查的类型以及新条目是否应该替换现有条目。 如果 **CreateEntry** 由于提供程序强制进行重复条目检查而未能创建新对象，则不要期望看到返回错误或警告。 在这些条件下，提供程序将返回成功代码。 
  
如果你直接使用容器并且确切知道容器可以创建的地址类型，可以调用 **IABContainer：：CreateEntry** 并传递相应模板的条目标识符。 通讯簿提供程序设置一些初始默认属性;可以调用 **SetProps** 来设置其他设置。 用户从不参与。 
  

