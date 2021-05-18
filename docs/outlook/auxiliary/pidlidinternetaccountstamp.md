---
title: PidLidInternetAccountStamp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 52003a4e-1b61-2965-5204-6601652dd15b
description: 返回传递邮件的帐户的帐户标记。
ms.openlocfilehash: c5da45268cefbe09588fdcfcda32e4e7a4be9d5f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327725"
---
# <a name="pidlidinternetaccountstamp"></a>PidLidInternetAccountStamp

返回传递邮件的帐户的帐户标记。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|相关属性：  <br/> |dispidInetAcctStamp  <br/> |
|属性集：  <br/> |PSETID_Common  <br/> |
|LONG ID (的一) ：  <br/> |0x00008581  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

此属性应包含从传递邮件的帐户的 Account Management API [PROP_ACCT_STAMP](prop_acct_stamp.md) 返回的相同值。 
  
邮件存储提供程序公开此命名属性 [和 PidLidInternetAccountName，](pidlidinternetaccountname.md) 以便发生以下操作： 
  
- 当用户 **单击电子邮件** 中的"全部答复"时，Outlook删除与帐户关联的电子邮件地址，并从回复的收件人列表中在邮件上标记该地址。 除非此电子邮件地址是原始邮件的发件人，否则会发生此行为。 
    
- 默认情况下，Outlook通过原始邮件上标记的帐户发送答复和转发的邮件。
    
通常，Outlook协议管理器传递邮件，Outlook 设置 **PidLidInternetAccountName** 和 **PidLidInternetAccountStamp** 属性以指示传递邮件的帐户。 但是，如果邮件存储与传输紧密结合，Outlook管理器不会传递邮件，Outlook设置这些属性。 在此方案中，Outlook [IMAPIProp：：GetIDsFromNames](https://msdn.microsoft.com/library/e3f501a4-a8ee-43d7-bd83-c94e7980c398%28Office.15%29.aspx)函数。 如果邮件存储提供程序想要公开这些命名属性，它应实现 **IMAPIProp：：GetIDsFromNames** 并通过输出参数  *lppPropTags*  返回属性标记。 Outlook可以使用这些属性标记调用[IMAPIProp：：GetProps](https://msdn.microsoft.com/library/1c7a9cd2-d765-4218-9aee-52df1a2aae6c%28Office.15%29.aspx)方法，并且消息存储提供程序可以返回所需帐户的帐户名称和标记。 
  
为了支持这些命名属性，存储提供程序应该Outlook **IMAPIProp：：GetIDsFromNames** 来获取此属性的属性标记。 Outlook为对应于此命名属性的 [MAPINAMEID](https://msdn.microsoft.com/library/9a92e9cd-8282-4cf0-93af-4089b3763594%28Office.15%29.aspx)结构指定以下值，该属性作为 **IMAPIProp：：GetIDsFromNames** 的输入参数 *lppPropNames* 指向的数组的一部分传递。 
  
|||
|:-----|:-----|
|lpGuid：  <br/> |PSETID_Common  <br/> |
|ulKind：  <br/> |MNID_ID  <br/> |
|Kind.lID：  <br/> |dispidInetAcctStamp  <br/> |
   
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)
- [PidLidInternetAccountStamp 规范属性](https://msdn.microsoft.com/library/819179fe-e58e-415c-abc7-1949036745ee%28Office.15%29.aspx)

