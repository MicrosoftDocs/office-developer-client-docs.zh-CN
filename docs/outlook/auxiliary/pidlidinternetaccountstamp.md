---
title: PidLidInternetAccountStamp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 52003a4e-1b61-2965-5204-6601652dd15b
description: 返回发送邮件的帐户的帐户戳。
ms.openlocfilehash: ba54bffb60a05a3b4a1ff30519960740af93ebd3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774421"
---
# <a name="pidlidinternetaccountstamp"></a>PidLidInternetAccountStamp

返回发送邮件的帐户的帐户戳。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|相关属性：  <br/> |dispidInetAcctStamp  <br/> |
|属性进行设置：  <br/> |PSETID_Common  <br/> |
|长 ID （盖）：  <br/> |0x00008581  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>说明

此属性应包含从发送邮件的帐户的帐户管理 API 属性[PROP_ACCT_STAMP](prop_acct_stamp.md)返回的值相同。 
  
消息存储提供程序公开此命名的属性和[PidLidInternetAccountName](pidlidinternetaccountname.md) ，以便执行以下操作： 
  
- 当用户在电子邮件中单击**全部答复**时，Outlook 将删除与该帐户相关联，并从收件人列表的答复邮件上标记的电子邮件地址。 除非此电子邮件地址是原始邮件的发件人，将发生此问题。 
    
- 默认情况下，Outlook 发送答复和转发的邮件通过标原始邮件上的帐户。
    
通常，Outlook 协议经理提供了邮件，和 Outlook 设置**PidLidInternetAccountName**和**PidLidInternetAccountStamp**属性来指示发送邮件的帐户。 但是，如果与传输紧密耦合的消息存储，Outlook 协议经理不传递邮件和 Outlook 无法设置这些属性。 在此方案中，Outlook 调用[IMAPIProp::GetIDsFromNames](http://msdn.microsoft.com/library/e3f501a4-a8ee-43d7-bd83-c94e7980c398%28Office.15%29.aspx)函数。 如果希望公开这些命名的属性的消息存储提供程序，它应实现**IMAPIProp::GetIDsFromNames**并返回通过输出参数*lppPropTags*属性标记。 Outlook 可通过使用这些属性标记，然后调用[IMAPIProp::GetProps](http://msdn.microsoft.com/library/1c7a9cd2-d765-4218-9aee-52df1a2aae6c%28Office.15%29.aspx)方法和消息存储提供程序可以返回帐户名和图章的所需的帐户。 
  
若要支持这些命名属性，存储提供程序应产生预期 Outlook 使用**IMAPIProp::GetIDsFromNames**来获取此属性的属性标记。 Outlook 指定下列值对应于作为由**IMAPIProp::GetIDsFromNames**输入的参数*lppPropNames*指向在数组的一部分传递此命名属性的[MAPINAMEID](http://msdn.microsoft.com/library/9a92e9cd-8282-4cf0-93af-4089b3763594%28Office.15%29.aspx)结构。 
  
|||
|:-----|:-----|
|lpGuid:  <br/> |PSETID_Common  <br/> |
|ulKind:  <br/> |MNID_ID  <br/> |
|Kind.lID:  <br/> |dispidInetAcctStamp  <br/> |
   
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)
- [PidLidInternetAccountStamp 规范属性](http://msdn.microsoft.com/library/819179fe-e58e-415c-abc7-1949036745ee%28Office.15%29.aspx)

